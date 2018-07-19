---
title: NMAKE の致命的なエラー U1070 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1070
dev_langs:
- C++
helpviewer_keywords:
- U1070
ms.assetid: 8639fc39-b4b1-48f5-ac91-0e9fb61680fd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1fe39a5d6f6074596561cd8e32f7b9428bc60f6d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33327042"
---
# <a name="nmake-fatal-error-u1070"></a>NMAKE の致命的なエラー U1070
マクロ定義 'macroname' に循環があります。  
  
 指定されたマクロの定義には、定義に含まれるには、指定されたマクロが含まれているマクロが含まれています。 循環マクロ定義が無効です。  
  
## <a name="example"></a>例  
 次のマクロ定義  
  
```  
ONE=$(TWO)  
TWO=$(ONE)  
```  
  
 次のエラーが発生します。  
  
```  
cycle in macro definition 'TWO'  
```