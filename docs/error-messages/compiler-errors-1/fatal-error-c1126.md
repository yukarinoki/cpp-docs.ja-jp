---
title: 致命的なエラー C1126 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1126
dev_langs:
- C++
helpviewer_keywords:
- C1126
ms.assetid: f22b26a6-8ad7-47cf-a237-196c8ea60aca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2a3ff02d69679074186e593d5e1c16bdf56d1052
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1126"></a>致命的なエラー C1126
'identifier': 自動メモリ割り当てサイズを超えています  
  
 関数 (swappable 関数の追加の 20 バイトなど、コンパイラで使用される領域の制限時間を加えた) のローカル変数に割り当てられた領域を超えています。  
  
 このエラーを解決するには使用`malloc`または`new`大量のデータを割り当てることです。