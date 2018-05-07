---
title: 致命的なエラー C1013 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1013
dev_langs:
- C++
helpviewer_keywords:
- C1013
ms.assetid: 5514a679-efe7-4055-bdd3-5693ca0c332f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 00b5dae643ec20e9d7d8a8dcdf41d9debe7e6b7e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1013"></a>致命的なエラー C1013
コンパイラの制限 : 始めかっこが多すぎます。  
  
 1 つの式で使用されているかっこのレベルが多すぎます。 式を簡略化するか、複数のステートメントに分割してください。  
  
 Visual C++ 6.0 Service Pack 3 以前のバージョンでは、1 つの式で使用できるかっこの入れ子は 59 に制限されています。 現在のかっこの入れ子は 256 に制限されています。