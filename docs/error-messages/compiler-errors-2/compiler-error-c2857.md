---
description: 詳細については、「コンパイラエラー C2857」を参照してください。
title: コンパイラ エラー C2857
ms.date: 09/13/2018
f1_keywords:
- C2857
helpviewer_keywords:
- C2857
ms.assetid: b57302bd-58ec-45ae-992a-1e282d5eeccc
ms.openlocfilehash: 85f2a9cffc8a96998a102d9e8219d9656cb3386f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337530"
---
# <a name="compiler-error-c2857"></a>コンパイラ エラー C2857

> /Yc *filename* コマンドラインオプションで指定された ' #include ' ステートメントがソースファイルに見つかりませんでした

[/Yc](../../build/reference/yc-create-precompiled-header-file.md)オプションは、コンパイルするソースファイルに含まれていないインクルードファイルの名前を指定します。

## <a name="remarks"></a>解説

ソースファイルで **/yc**<em>filename</em> オプションを使用してプリコンパイル済みヘッダー (PCH) ファイルを作成する場合、そのソースファイルには *filename* ヘッダーファイルが含まれている必要があります。 ソースファイルに含まれるすべてのファイルは、指定されたファイル *名* を含めて、PCH ファイルに含まれます。 PCH ファイルを使用するために **/yu**<em>filename</em> オプションを使用してコンパイルされた他のソースファイルでは、ファイル *名* のインクルードがファイルのコメント以外の最初の行である必要があります。 コンパイラは、このインクルードの前に、ソースファイル内のすべてのものを無視します。

このエラーは、 `#include "filename"` PCH ソースファイルでコンパイルされていない条件付きコンパイルブロックのステートメントが原因で発生する場合があります。

## <a name="example"></a>例

一般的な使用方法では、プロジェクト内の1つのソースファイルが PCH ソースファイルとして指定され、1つのヘッダーファイルが PCH ヘッダーファイルとして使用されます。 一般的な PCH ヘッダーファイルには、プロジェクトで使用されているすべてのライブラリヘッダーがありますが、まだ開発中のローカルヘッダーは含まれていません。 このサンプルでは、PCH ヘッダーファイルに *my_pch .h* という名前が付けられています。

```cpp
// my_pch.h
#pragma once
#include <stdio.h>
```

PCH ソースファイルは、 **/yc**<em>my_pch</em> オプションを使用してコンパイルされます。 この PCH ヘッダーファイルが見つからない場合、コンパイラは C2857 を生成します。

```cpp
// my_pch.cpp
// Compile by using: cl /EHsc /W4 /Yumy_pch.h /c my_pch.cpp

#if 0
#include "my_pch.h"  // C2857; remove conditional directives to fix
#endif
```

この PCH ファイルを使用するには、 **/yu**<em>my_pch. h</em> オプションを使用してソースファイルをコンパイルする必要があります。 Pch を使用するソースファイルには、まず PCH ヘッダーファイルが含まれている必要があります。

```cpp
// C2857.cpp
// Compile my_pch.cpp first, then
// compile by using: cl /EHsc /W4 /Yumy_pch.h my_project.cpp my_pch.obj
// Include the pch header before any other non-comment line
#include "my_pch.h"

int main()
{
    puts("Using a precompiled header file.\n");
}
```
