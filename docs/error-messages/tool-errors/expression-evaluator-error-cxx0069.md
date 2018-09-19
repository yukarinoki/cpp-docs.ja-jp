---
title: 式エバリュエーター エラー CXX0069 |Microsoft Docs
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
ms.openlocfilehash: 9a3efb6432f536ecb929c8ff8670d31030b569b7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46112734"
---
# <a name="expression-evaluator-error-cxx0069"></a>式エバリュエーター エラー CXX0069

変数には、スタック フレームが必要です。

スタック フレームが発生しないために、式エバリュエーターは、変数を評価できません。 これは、インライン関数の一部として宣言された変数によって発生する可能性があります。