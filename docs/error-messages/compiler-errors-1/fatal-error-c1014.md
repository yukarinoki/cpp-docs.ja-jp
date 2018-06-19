---
title: 致命的なエラー C1014 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1014
dev_langs:
- C++
helpviewer_keywords:
- C1014
ms.assetid: 4c01ef70-e765-4d07-a3fe-a11c19fb610b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b52f0d998e124412c3cf81de4efa762d1c0c346e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33224812"
---
# <a name="fatal-error-c1014"></a>致命的なエラー C1014
インクルード ファイルが多すぎます : 深さ = level  
  
 `#include` ディレクティブの入れ子が深すぎます。 入れ子になったディレクティブには、開いているファイルを含めることができます。 ディレクティブが含まれているソース ファイルは、1 つのファイルとしてカウントされます。