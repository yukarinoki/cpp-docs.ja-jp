---
title: 式エバリュエーター エラー CXX0039 |Microsoft Docs
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
ms.openlocfilehash: b5397426618c5dfcbaa6307105781ff2e6f2eb97
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46048332"
---
# <a name="expression-evaluator-error-cxx0039"></a>式エバリュエーター エラー CXX0039

シンボルがあいまいです。

C の式エバリュエーターでは、式で使用するシンボルのどのインスタンスを特定できません。 シンボルは、継承ツリー内で複数回に発生します。

スコープ解決演算子を使用する必要があります (`::`)、式で使用するインスタンスを明示的に指定します。

このエラーは、can0039 と同じものと同じです。