---
title: 致命的なエラー C1852 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1852
dev_langs:
- C++
helpviewer_keywords:
- C1852
ms.assetid: fa011004-b8d6-46f1-ba80-4785e4ce137f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d11160eea5e978a0c1ef67255d4e96b48fe2d101
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1852"></a>致命的なエラー C1852
'filename' は有効なプリコンパイル済みヘッダー ファイルではありません  
  
 ファイルはプリコンパイル済みヘッダーではありません。  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには  
  
1.  **/Yu** または **#pragma hdrstop**で指定された無効なファイル。  
  
2.  特に指定がない場合、コンパイラはファイル拡張子を .pch と想定します。