# Migration `20200502172215-recordedat`

This migration has been generated by fabianmoronzirfas at 5/2/2020, 5:22:15 PM.
You can check out the [state of the schema](./schema.prisma) after the migration.

## Database Steps

```sql
ALTER TABLE "public"."Record" DROP COLUMN "recordedAt";
```

## Changes

```diff
diff --git schema.prisma schema.prisma
migration 20200414065052-desc..20200502172215-recordedat
--- datamodel.dml
+++ datamodel.dml
@@ -2,9 +2,9 @@
 // learn more about it in the docs: https://pris.ly/d/prisma-schema
 datasource db {
   provider = "postgresql"
-  url = "***"
+  url      = env("DATABASE_URL")
 }
 generator client {
   provider = "prisma-client-js"
@@ -21,9 +21,9 @@
 // https://learn.pimoroni.com/tutorial/sandyj/getting-started-with-enviro-plus
 model Record {
   id Int @default(autoincrement()) @id
   createdAt DateTime @default(now())
-  recordedAt DateTime
+  // recordedAt DateTime
   collector Collector  @relation(fields: [collectorId], references: [id])
   collectorId  Int
   temperature Float?
   pressure Float?
```


