---
title: コンパイラの警告 (レベル 1) C4742
ms.date: 11/04/2016
f1_keywords:
- C4742
helpviewer_keywords:
- C4742
ms.assetid: e520881d-1eeb-48b1-9df0-8017ee8ba076
ms.openlocfilehash: af97c72f496177d2e94cf18f9685ac33c5e62404
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80185660"
---
# <a name="compiler-warning-level-1-c4742"></a>コンパイラの警告 (レベル 1) C4742

' file1 ' と ' file2 ' では、' var ' の配置が異なります。数値と数値

2つのファイルで参照または定義された外部変数は、それらのファイル内で異なるアラインメントを持ちます。 この警告は、コンパイラが*file1*の変数の `__alignof` が*file2*の変数の `__alignof` と異なることを検出した場合に生成されます。 異なるファイルで変数を宣言するとき、または異なるファイルで一致しない `#pragma pack` を使用することによって、互換性のない型を使用することが原因である可能性があります。

この警告を解決するには、同じ型定義を使用するか、変数に別の名前を使用します。

詳細については、「 [pack](../../preprocessor/pack.md) And [__alignof Operator](../../cpp/alignof-operator.md)」を参照してください。

## <a name="example"></a>例

これは、型を定義する最初のファイルです。

```c
// C4742a.c
// compile with: /c
struct X {
   char x, y, z, w;
} global;
```

## <a name="example"></a>例

次の例では、C4742 が生成されます。

```c
// C4742b.c
// compile with: C4742a.c /W1 /GL
// C4742 expected
extern struct X {
   int a;
} global;

int main() {
   global.a = 0;
}
```
