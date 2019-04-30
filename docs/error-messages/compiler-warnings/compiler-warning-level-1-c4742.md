---
title: コンパイラの警告 (レベル 1) C4742
ms.date: 11/04/2016
f1_keywords:
- C4742
helpviewer_keywords:
- C4742
ms.assetid: e520881d-1eeb-48b1-9df0-8017ee8ba076
ms.openlocfilehash: 00ac67fec3aafa5a259b5222bd6bb8654210fa61
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62390426"
---
# <a name="compiler-warning-level-1-c4742"></a>コンパイラの警告 (レベル 1) C4742

'var' が 'file1' および 'file2' 内で異なるアラインメント: 番号と番号

参照または 2 つのファイルで定義された外部変数は、それらのファイルで異なるアラインメントをいます。 この警告は、コンパイラが検索するときに生成されます`__alignof`に変数の*file1*とは異なります`__alignof`に変数の*file2*します。 別のファイルで変数を宣言するときに、互換性のない型を使用して、または一致しないを使用してこれを発生することができます`#pragma pack`複数のファイル。

この警告を解決するには、同じ種類の定義を使用するか異なる名前の変数を使用します。

詳細については、次を参照してください。[パック](../../preprocessor/pack.md)と[_ _alignof 演算子](../../cpp/alignof-operator.md)します。

## <a name="example"></a>例

これは、型を定義する最初のファイルです。

```
// C4742a.c
// compile with: /c
struct X {
   char x, y, z, w;
} global;
```

## <a name="example"></a>例

次の例では、C4742 が生成されます。

```
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