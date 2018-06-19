---
title: 式エバリュエーター エラー CXX0039 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0039
dev_langs:
- C++
helpviewer_keywords:
- CXX0039
- CAN0039
ms.assetid: 8bf698d2-e015-4595-944f-72b81aa43d22
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8681d73d2889433516b205a47c500193bbeabdb0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33297769"
---
# <a name="expression-evaluator-error-cxx0039"></a>式エバリュエーター エラー CXX0039
シンボルがあいまいです。  
  
 C の式エバリュエーターは、式で使用するシンボルのインスタンスを特定できません。 シンボルは、継承ツリー内で複数回発生します。  
  
 スコープ解決演算子を使用する必要があります (`::`)、式で使用するインスタンスを明示的に指定します。  
  
 このエラーは、can0039 と同じものと同じです。