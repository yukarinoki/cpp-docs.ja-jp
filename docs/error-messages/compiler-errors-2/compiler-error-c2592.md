---
title: コンパイラ エラー C2592 |Microsoft ドキュメント
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
ms.openlocfilehash: 5d999056d718d9c7aad93d08a99895caebbef539
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33229814"
---
# <a name="compiler-error-c2592"></a>コンパイラ エラー C2592
'class': 'base_class_2' は、'base_class_1' から継承されるので、再指定することはできません  
  
 他の基底クラスから継承していない基底クラスのみを指定できます。 この場合は、`base_class_1` が既に `base_class_2` を継承しているため、`class` の指定で必要になるのは `base_class_1` のみです。