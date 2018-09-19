---
title: コンパイラ エラー C2592 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2592
dev_langs:
- C++
helpviewer_keywords:
- C2592
ms.assetid: 833a4d7b-66ef-4d4c-ae83-a533c2b0eb07
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3f2377f48eb8102771705f2dedc67a7a15f6fa95
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46030990"
---
# <a name="compiler-error-c2592"></a>コンパイラ エラー C2592

'class': 'base_class_2' は、'base_class_1' から継承されるので、再指定することはできません

他の基底クラスから継承していない基底クラスのみを指定できます。 この場合は、`base_class_1` が既に `base_class_2` を継承しているため、`class` の指定で必要になるのは `base_class_1` のみです。