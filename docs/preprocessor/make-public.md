---
description: pragmaMicrosoft C/c + + での make_public ディレクティブの詳細については、こちらを参照してください。
title: make_public pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.make_public
- make_public_CPP
helpviewer_keywords:
- pragma, make_public
- make_public pragma
no-loc:
- pragma
ms.openlocfilehash: 4bc3370ac0901ff9a0656de5657f9c9f557e1dff
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713520"
---
# <a name="make_public-no-locpragma"></a>`make_public` pragma

ネイティブ型はパブリック アセンブリのアクセシビリティが必要であることを示します。

## <a name="syntax"></a>構文

> **`#pragma make_public(`***型***`)`**

### <a name="parameters"></a>パラメーター

*type*\
パブリックアセンブリのアクセシビリティを設定する型の名前。

## <a name="remarks"></a>解説

**`make_public`** は、参照するネイティブ型が、変更できないヘッダーファイルからのものである場合に便利です。 パブリック関数のシグネチャでネイティブ型を使用する場合は、公開されている型のアセンブリの参照可能範囲を使用する必要があります。または、ネイティブ型にパブリックアセンブリのアクセシビリティがあること、またはコンパイラが警告を発行する必要があります。

**`make_public`** グローバルスコープで指定する必要があります。 これは、ソースコードファイルの末尾までを通じて宣言されているポイントからのみ有効です。

ネイティブ型は、暗黙的または明示的にプライベートにすることができます。 詳細については、「 [型の可視性](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility)」を参照してください。

## <a name="examples"></a>例

次の例は、2つのネイティブ構造体の定義を含むヘッダーファイルの内容を示しています。

```cpp
// make_public_pragma.h
struct Native_Struct_1 { int i; };
struct Native_Struct_2 { int i; };
```

次のコードサンプルでは、ヘッダーファイルを使用します。 これは、を使用してネイティブ構造体をパブリックとして明示的にマークしない限り、パブリックな **`make_public`** マネージ型のパブリック関数のシグネチャでネイティブ構造体を使用しようとすると、コンパイラによって警告が生成されることを示しています。

```cpp
// make_public_pragma.cpp
// compile with: /c /clr /W1
#pragma warning (default : 4692)
#include "make_public_pragma.h"
#pragma make_public(Native_Struct_1)

public ref struct A {
   void Test(Native_Struct_1 u) {u.i = 0;}   // OK
   void Test(Native_Struct_2 u) {u.i = 0;}   // C4692
};
```

## <a name="see-also"></a>関連項目

[プラグマディレクティブと `__pragma` `_Pragma` キーワードおよびキーワード](./pragma-directives-and-the-pragma-keyword.md)
