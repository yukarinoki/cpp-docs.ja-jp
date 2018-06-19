---
title: コンパイラの警告 (レベル 1) C4025 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4025
dev_langs:
- C++
helpviewer_keywords:
- C4025
ms.assetid: c4f6a651-0641-4446-973e-8290065e49ad
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 47e84ba11c7bed7420a9a1c699361612ef2002d8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33273950"
---
# <a name="compiler-warning-level-1-c4025"></a>コンパイラの警告 (レベル 1) C4025
'number': _based ポインターが可変引数を伴う関数に渡されました。パラメーター番号  
  
 可変個の引数のある関数に _based ポインターを渡すと、ポインターが正規化され、予期しない結果が発生します。 可変個の引数のある関数に _based ポインターを渡さないでください。