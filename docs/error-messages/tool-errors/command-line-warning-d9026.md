---
title: コマンドラインの警告 D9026 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- D9026
dev_langs:
- C++
helpviewer_keywords:
- D9026
ms.assetid: 149fe5e3-5329-4be8-b871-49dfd423aaba
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9e2d99573ee46c51178cc2fe995fa0f526b800f9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="command-line-warning-d9026"></a>コマンド ラインの警告 D9026
オプションはコマンドライン全体に適用します。  
  
 オプションは、ファイル名の指定後、コマンドで指定されました。 オプションは、前に、ファイルに適用されました。  
  
 たとえば、コマンドで  
  
```  
CL verdi.c /G5 puccini.c  
```  
  
 /G4 デフォルトではありません、/G5 オプションを使用して、VERDI.c というファイルがコンパイルされます。  
  
 この動作は VERDI.c で結果として得られる、ファイル名の前に指定されたオプションを使用してコンパイル/G4 と異なりコンパイル/G5 を使用してのみに適用されるいくつか以前のバージョンの場合と異なります。