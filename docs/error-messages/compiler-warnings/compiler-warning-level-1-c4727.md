---
title: コンパイラの警告 (レベル 1) C4727
ms.date: 08/19/2019
f1_keywords:
- C4727
helpviewer_keywords:
- C4727
ms.assetid: 991b0087-3a50-40f5-9cdb-cdc367cd472c
ms.openlocfilehash: 0c00ac552e525fd57f6f09b0be5655958cfce3cc
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80075142"
---
# <a name="compiler-warning-level-1-c4727"></a>コンパイラの警告 (レベル 1) C4727

"Obj_file_1 と obj_file_2 で同じタイムスタンプを持つ pch_file という名前の PCH が見つかりました。  最初の PCH を使用します。

> [!NOTE]
> Visual Studio 2017 以前では、プリコンパイル済みヘッダーは既定で*stdafx.h*と呼ばれており、visual studio 2019 以降では既定で*pch*と呼ばれています。

C4727 は、 **/yc**を使用して複数の compilands をコンパイルするとき、およびコンパイラが同じ .pch タイムスタンプですべての .obj ファイルをマークできるようになったときに発生します。

解決するには、 **/yc/c** (pch を作成) を使用して1つのソースファイルをコンパイルし、その他のファイルを **/yu/c** (pch を使用) で個別にコンパイルしてから、それらをリンクします。

次のようにした場合、C4727 が生成されます。

::: moniker range="<=vs-2017"

**cl/clr/GL a .cpp b. .cpp/Ycstdafx.h**

代わりに、次の操作を行います。

**cl/clr/GL/Ycstdafx.h/c**

**cl/clr/GL b .cpp/Yustdafx.h (/link)**

::: moniker-end

::: moniker range=">=vs-2019"

**cl/clr/GL a .cpp b. .cpp/Ycpch.h**

代わりに、次の操作を行います。

**cl/clr/GL/Ycpch.h/c**

**cl/clr/GL b .cpp/Yupch.h (/link)**

::: moniker-end

詳細については、「

- [/Yc (プリコンパイル済みヘッダー ファイルの作成)](../../build/reference/yc-create-precompiled-header-file.md)

- [/Yu (プリコンパイル済みヘッダー ファイルの使用)](../../build/reference/yu-use-precompiled-header-file.md)