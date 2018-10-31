---
title: make_public |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.make_public
- make_public_CPP
dev_langs:
- C++
helpviewer_keywords:
- pragmas, make_public
- make_public pragma
ms.assetid: c3665f4d-268a-4932-9661-c37c8ae6a341
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eeabbfac65e67e0a293f4c31ff6f8911cc0b676e
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50066722"
---
# <a name="makepublic"></a>make_public
ネイティブ型はパブリック アセンブリのアクセシビリティが必要であることを示します。

## <a name="syntax"></a>構文

```
#pragma make_public(type)
```

### <a name="parameters"></a>パラメーター

*型*パブリック アセンブリ アクセシビリティを持つ型の名前を指定します。

## <a name="remarks"></a>Remarks

**make_public**は変更できない .h ファイルから参照するネイティブな型の場合に適しています。 パブリック関数のシグニチャでパブリック アセンブリ可視性を持つ型としてネイティブ型を使用する場合は、ネイティブ型にパブリック アセンブリ アクセシビリティもある必要があります。そうでない場合、コンパイラは警告を発行します。

**make_public**グローバル スコープで指定する必要があり、あり、宣言されてからソース コード ファイルの末尾にのみ、ポイントから有効です。

ネイティブな型が暗黙的または明示的に private 可能性があります。参照してください[型の可視性](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility)詳細についてはします。

## <a name="examples"></a>使用例

次のサンプルは、2 つのネイティブ構造体の定義を含む .h ファイルの内容です。

```cpp
// make_public_pragma.h
struct Native_Struct_1 { int i; };
struct Native_Struct_2 { int i; };
```

次のコード サンプル、ヘッダー ファイルを使用し、明示的にマークする、パブリックとしてネイティブ構造体を使用しない限り、ことを示しています**make_public**コンパイラでネイティブ構造体を使用しようとしたときに警告が生成されます、パブリック マネージ型のパブリック関数のシグネチャです。

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

[プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)