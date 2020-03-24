---
title: 致命的なエラー C1852
ms.date: 11/04/2016
f1_keywords:
- C1852
helpviewer_keywords:
- C1852
ms.assetid: fa011004-b8d6-46f1-ba80-4785e4ce137f
ms.openlocfilehash: 540febabc8f2947f11b58cf7eadee53d47f7bef3
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80202879"
---
# <a name="fatal-error-c1852"></a>致命的なエラー C1852

'filename' は有効なプリコンパイル済みヘッダー ファイルではありません

ファイルはプリコンパイル済みヘッダーではありません。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. **/Yu** または **#pragma hdrstop**で指定された無効なファイル。

1. 特に指定がない場合、コンパイラはファイル拡張子を .pch と想定します。
