---
title: 致命的なエラー C1013 |Microsoft Docs
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
ms.openlocfilehash: 33c10062cac83984fb1c68835780497b89c4cbc1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46050522"
---
# <a name="fatal-error-c1013"></a>致命的なエラー C1013

コンパイラの制限 : 始めかっこが多すぎます。

1 つの式で使用されているかっこのレベルが多すぎます。 式を簡略化するか、複数のステートメントに分割してください。

Visual C++ 6.0 Service Pack 3 以前のバージョンでは、1 つの式で使用できるかっこの入れ子は 59 に制限されています。 現在のかっこの入れ子は 256 に制限されています。