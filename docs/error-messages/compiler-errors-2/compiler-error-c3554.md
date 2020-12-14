---
description: 詳細については、「コンパイラエラー C3554」を参照してください。
title: コンパイラ エラー C3554
ms.date: 11/04/2016
f1_keywords:
- C3554
helpviewer_keywords:
- C3554
ms.assetid: aede18d5-fefc-4da9-9b69-adfe90bfa742
ms.openlocfilehash: 39bc1a673af37d6b73941bb300d86df5f41a4704
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97223179"
---
# <a name="compiler-error-c3554"></a>コンパイラ エラー C3554

'decltype' を他の型指定子と組み合わせることはできません

型指定子を使用して `decltype()` キーワードを修飾することはできません。 たとえば、次のコード フラグメントではエラー C3554 が生成されます。

```
int x;
unsigned decltype(x); // C3554
```
