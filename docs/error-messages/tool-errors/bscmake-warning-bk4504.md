---
title: BSCMAKE の警告 BK4504
ms.date: 11/04/2016
f1_keywords:
- BK4504
helpviewer_keywords:
- BK4504
ms.assetid: b56ee2d4-ad44-40f4-98c0-75934ea44a6c
ms.openlocfilehash: 57858827439ac8cc11e3718d7a484124ae8a6d74
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80197445"
---
# <a name="bscmake-warning-bk4504"></a>BSCMAKE の警告 BK4504

ファイルに含まれている参照が多すぎます。このソースからのその他の参照を無視します

.Cpp ファイルに64000個を超えるシンボル参照が含まれています。 BSCMAKE によってファイル内で64000の参照が検出されると、それ以降のすべての参照が無視されます。

この問題を解決するには、ファイルを2つ以上のファイルに分割します。それぞれのシンボル参照が64000未満であるか、`#pragma component(browser)` プリプロセッサディレクティブを使用して、特定の参照に対して生成されるシンボルを制限します。 詳細については、「 [component](../../preprocessor/component.md)」を参照してください。
