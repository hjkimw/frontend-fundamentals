# Simplifying Ternary Operators

<div style="margin-top: 16px">
<Badge type="info" text="Readability" />
</div>

Using complex ternary operators can obscure the structure of the conditions, making the code harder to read.

## 📝 Code Example

The following code assigns `'BOTH'`, `'A'`, or `'NONE'` to `status` based on `ACondition` and `BCondition`.

```typescript
const status = ACondition && BCondition ? "BOTH" : NotBoth ? "NONE" : ACondition ? "A" : undefined;
```

## 👃 Smell the Code

### Readability

This code uses multiple nested ternary operators, making it difficult to quickly understand the exact conditions under which values are calculated.

## ✏️ Work on Improving

You can rewrite the conditions using `if` statements, as shown below, to make the logic clearer and easier to follow.

```typescript
const status = useMemo(() => {
  if (ACondition && BCondition) {
   return "BOTH";
 }

 if (ACondition) {
   return "A";
 }

 return "NONE";
}, [ACondition, BCondition]);
```