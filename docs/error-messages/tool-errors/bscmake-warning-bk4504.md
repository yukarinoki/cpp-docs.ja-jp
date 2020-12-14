---
description: 詳細については、「BSCMAKE Warning BK4504」を参照してください。
title: BSCMAKE の警告 BK4504
ms.date: 11/04/2016
f1_keywords:
- BK4504
helpviewer_keywords:
- BK4504
ms.assetid: b56ee2d4-ad44-40f4-98c0-75934ea44a6c
ms.openlocfilehash: 8b07c15b03a040ea19ec368c6f869d02f3e36f79
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97237830"
---
# <a name="bscmake-warning-bk4504"></a>BSCMAKE の警告 BK4504

ファイルに含まれている参照が多すぎます。このソースからのその他の参照を無視します

.Cpp ファイルに64000個を超えるシンボル参照が含まれています。 BSCMAKE によってファイル内で64000の参照が検出されると、それ以降のすべての参照が無視されます。

この問題を解決するには、ファイルを2つ以上のファイルに分割します。それぞれのシンボル参照が64000未満であるか、プリプロセッサディレクティブを使用して、 `#pragma component(browser)` 特定の参照に対して生成されるシンボルを制限します。 詳細については、「 [component](../../preprocessor/component.md)」を参照してください。
