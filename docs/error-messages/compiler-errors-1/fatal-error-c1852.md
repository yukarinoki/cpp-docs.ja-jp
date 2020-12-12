---
description: '詳細情報: 致命的なエラー C1852'
title: 致命的なエラー C1852
ms.date: 11/04/2016
f1_keywords:
- C1852
helpviewer_keywords:
- C1852
ms.assetid: fa011004-b8d6-46f1-ba80-4785e4ce137f
ms.openlocfilehash: 0b4976566b8101ecd4f35d20854ef6124a15246e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97276245"
---
# <a name="fatal-error-c1852"></a>致命的なエラー C1852

'filename' は有効なプリコンパイル済みヘッダー ファイルではありません

ファイルはプリコンパイル済みヘッダーではありません。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. **/Yu** または **#pragma hdrstop** で指定された無効なファイル。

1. 特に指定がない場合、コンパイラはファイル拡張子を .pch と想定します。
