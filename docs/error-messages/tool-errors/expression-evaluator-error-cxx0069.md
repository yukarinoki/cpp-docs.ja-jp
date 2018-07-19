---
title: 式エバリュエーター エラー CXX0069 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0069
dev_langs:
- C++
helpviewer_keywords:
- CXX0069
ms.assetid: cf334b23-1e17-4d37-acc5-18597ee84164
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 14cf468ebd2d8d40f306a2fa80a0331d7667d0d4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33299667"
---
# <a name="expression-evaluator-error-cxx0069"></a>式エバリュエーター エラー CXX0069
変数には、スタック フレームが必要です。  
  
 スタック フレームが発生しないために、式エバリュエーターは、変数を評価できません。 インライン関数の一部として宣言された変数が考えられます。