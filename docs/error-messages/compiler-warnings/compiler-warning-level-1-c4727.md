---
title: コンパイラの警告 (レベル 1) C4727 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4727
dev_langs:
- C++
helpviewer_keywords:
- C4727
ms.assetid: 991b0087-3a50-40f5-9cdb-cdc367cd472c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b9d169ec9d08f06831370fa68c4049076dbfc582
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46053740"
---
# <a name="compiler-warning-level-1-c4727"></a>コンパイラの警告 (レベル 1) C4727

"PCH obj_file_1 や obj_file_2 で同じタイムスタンプを持つ pch_file をという名前です。  最初の PCH を使用します。

C4727 で複数のコンパイル単位をコンパイルするときに発生します。 **/Yc**、およびコンパイラが同じ .pch タイムスタンプを持つすべての .obj ファイルをマークできません。

を解決するには、1 つのソース ファイルをコンパイル **/Yc/c** (pch を作成します) を使用して個別にコンパイル、他のユーザーと **/Yu/c** (pch を使用)、それらをリンクします。

そのため、以下し、C4727 を生成する場合。

**cl/clr/GL a.cpp b.cpp c.cpp/Ycstdafx.h**

次の代わりに実行します。

**cl/clr/GL a.cpp/Ycstdafx.h/c**

**cl/clr/GL b.cpp c.cpp/Yustdafx.h/link a.obj**

詳細については、次のトピックを参照してください。

- [/Yc (プリコンパイル済みヘッダー ファイルの作成)](../../build/reference/yc-create-precompiled-header-file.md)

- [/Yu (プリコンパイル済みヘッダー ファイルの使用)](../../build/reference/yu-use-precompiled-header-file.md)