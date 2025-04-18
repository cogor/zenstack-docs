---
description: Enhancements to the types generated by Prisma
sidebar_position: 4
sidebar_label: Enhanced Prisma Types
---

# Enhanced Prisma Types

When you call the [`enhance`](./runtime-api#enhance) API, ZenStack not only enhances `PrismaClient`'s runtime behavior, but also alters its types as needed. For example, when you use [polymorphic models](../guides/polymorphism), ZenStack translates the inheritance hierarchy into a proper Prisma schema following the [Multi-table inheritance](https://www.prisma.io/docs/orm/prisma-schema/data-model/table-inheritance#multi-table-inheritance-mti) pattern, however it keeps the typing of the enhanced `PrismaClient` simple and provides a real "polymorphic" DX.

You usually don't need to explicitly refer to the enhanced Prisma types, but when you need, import them from the `@zenstackhq/runtime/models` module instead of `@prisma/client`.

```ts
import type { Post, Prisma } from '@zenstackhq/runtime/models'
import { getEnhancedPrisma } from '~/db'

const db = getEnhancedPrisma();

// explicitly refer to the enhanced model type
const post: Post = await db.post.findUnique({...});

// explicitly refer to the enhanced input type
const createInput: Prisma.PostCreateInput = { ... };
await db.post.create({ data: createInput });
```

You can also use the `Enhanced` typing utility to infer the enhanced `PrismaClient` from its original typing:

```ts
import { PrismaClient } from '@prisma/client';
import type { Enhanced } from '@zenstackhq/runtime';

const prisma = new PrismaClient();

type EnhancedPrismaClient = Enhanced<typeof prisma>;
```

The `prisma` instance can be a raw `PrismaClient`, or one with Prisma Client Extensions installed.
