---
title: 致命的なエラー C1081 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1081
dev_langs:
- C++
helpviewer_keywords:
- C1081
ms.assetid: e58adf17-cbe1-4955-a5c7-80622bbba249
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4b5ea18ff3f2714d9621d4372cf541be2f9b225a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1081"></a>致命的なエラー C1081
'symbol': ファイル名が長すぎます  
  
 ファイルのパス名の長さを超えています`_MAX_PATH`(260 文字としては、STDLIB.h で定義) です。 ファイルの名前を短くしてください。  
  
 短いファイル名を持つ CL.exe を呼び出した場合、コンパイラは、完全なパス名を生成する必要があります。 たとえば、`cl -c myfile.cpp`を生成するコンパイラが発生する可能性があります。  
  
```  
D:\<very-long-directory-path>\myfile.cpp  
```