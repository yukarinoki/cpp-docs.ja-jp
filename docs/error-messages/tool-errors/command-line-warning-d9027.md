---
title: コマンドラインの警告 D9027 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- D9027
dev_langs:
- C++
helpviewer_keywords:
- D9027
ms.assetid: 2a29edc5-5649-48f2-9058-2057c747284c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dfe2493290c4e4cc5b744136b8e7036c6559220a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="command-line-warning-d9027"></a>コマンド ラインの警告 D9027
ソース ファイル '\<filename >' は無視されます  
  
 CL.exe には、入力ソース ファイルが無視されます。  
  
 この警告は、/Fo オプションと/c オプションを使用して、コマンド ラインで出力ファイル名の間をスペースで可能性があります。 例えば:  
  
```  
cl /c /Fo output.obj input.c   
```  
  
 /Fo 間にスペースがあるため、 `output.obj`、CL.exe は`output.obj`入力ファイルの名前として。 問題を解決するには、スペースを削除します。  
  
```  
cl /c /Fooutput.obj input.c   
```