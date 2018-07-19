---
title: コンパイラの警告 (レベル 4) C4513 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4513
dev_langs:
- C++
helpviewer_keywords:
- C4513
ms.assetid: 6877334a-f30a-4184-9483-dac3348737a4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 92c3e89204ec30f9c96a5ea03ede5093dd013d0c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33292897"
---
# <a name="compiler-warning-level-4-c4513"></a>コンパイラの警告 (レベル 4) C4513
'class': デストラクターを生成できませんでした  
  
 コンパイラは、指定したクラスの既定のデストラクターを生成できません。デストラクターは作成されませんでした。 デストラクターは基底クラスが派生クラスにアクセスできないことです。 基本クラスには private デストラクターがある場合は、public または protected ください。