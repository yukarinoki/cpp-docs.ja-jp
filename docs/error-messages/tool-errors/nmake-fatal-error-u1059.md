---
title: NMAKE の致命的なエラー U1059 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1059
dev_langs:
- C++
helpviewer_keywords:
- U1059
ms.assetid: b21d9198-9c63-40d0-b589-80e17294ce24
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6eb038befdb7c587c6fe2a734003abba585c3e2a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="nmake-fatal-error-u1059"></a>NMAKE の致命的なエラー U1059
構文エラー: '}' に依存するがありません  
  
 依存ファイルの検索パスが正しく指定されていません。 パスまたは右中かっこで空白が存在していた (**}**) は省略されました。  
  
 ディレクトリの仕様を相互に依存するための構文します。  
  
 **{**   
 ***ディレクトリ*} 依存**  
  
 ここで`directories`1 つまたは複数のパス、それぞれをセミコロンで区切って指定 (**;**)。 スペースは許可されません。  
  
 マクロで検索パスの一部または全体が置き換えられた場合、マクロ展開でスペースが存在しないことを確認します。