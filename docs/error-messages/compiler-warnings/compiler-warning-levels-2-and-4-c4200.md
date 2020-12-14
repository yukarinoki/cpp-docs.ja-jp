---
description: '詳細情報: コンパイラの警告 (レベル2および 4) C4200'
title: コンパイラの警告 (レベル 2 および 4) C4200
ms.date: 11/04/2016
f1_keywords:
- C4200
helpviewer_keywords:
- C4200
ms.assetid: e44d6073-937f-42b7-acc1-65e802b475c6
ms.openlocfilehash: 7068e98303049db4e64e46abbd9dae14c11395f6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234346"
---
# <a name="compiler-warning-levels-2-and-4-c4200"></a>コンパイラの警告 (レベル 2 および 4) C4200

非標準の拡張機能が使用されています : 構造体または共用体中にサイズが 0 の配列があります。

構造体または共用体がサイズが 0 の配列が含まれていることを示します。

サイズが 0 の配列の宣言は、Microsoft 拡張機能です。 これにより、C ファイルをコンパイルした場合はレベル 2 の警告、C++ ファイルをコンパイルした場合はレベル 4 の警告が発生します。 C++ のコンパイルでも、"UDT にサイズが 0 の配列が含まれているときに、copy-ctor または copy-assignment オペレーターを生成することはできません。" という警告が発生します。 次の例では警告 C4200 が生成されます。

```cpp
// C4200.cpp
// compile by using: cl /W4 c4200.cpp
struct A {
    int a[0];  // C4200
};
int main() {
}
```

この非標準の拡張機能は、可変長の外部データ構造とのインターフェイス コードによく使用されます。 コードがこのシナリオに該当する場合は、次のように警告を無効にできます。

## <a name="example"></a>例

```cpp
// C4200b.cpp
// compile by using: cl /W4 c4200a.cpp
#pragma warning(disable : 4200)
struct A {
    int a[0];
};
int main() {
}
```
