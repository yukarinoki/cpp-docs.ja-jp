---
title: コンパイラエラー C2095
ms.date: 11/04/2016
f1_keywords:
- C2095
helpviewer_keywords:
- C2095
ms.assetid: 44f8ada1-974f-4e81-a408-33ac6695aa53
ms.openlocfilehash: 327f4406be241f3aff89fd357fc103398401ea8f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80207663"
---
# <a name="compiler-error-c2095"></a>コンパイラエラー C2095

' function ': 実引数の型は ' void ' ですが、パラメーター ' number ' が指定されています。

関数に渡されたパラメーターが `void`型ですが、これは許可されていません。 代わりに、void (`void *`) へのポインターを使用してください。

`number` は、どのパラメーターが `void`かを示します。
