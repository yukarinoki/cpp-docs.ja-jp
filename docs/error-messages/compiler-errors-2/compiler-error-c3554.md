---
title: コンパイラ エラー C3554
ms.date: 11/04/2016
f1_keywords:
- C3554
helpviewer_keywords:
- C3554
ms.assetid: aede18d5-fefc-4da9-9b69-adfe90bfa742
ms.openlocfilehash: ecdb90e845714e046ed21cf5a200ef4548487df6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80200604"
---
# <a name="compiler-error-c3554"></a>コンパイラ エラー C3554

'decltype' を他の型指定子と組み合わせることはできません

型指定子を使用して `decltype()` キーワードを修飾することはできません。 たとえば、次のコード フラグメントではエラー C3554 が生成されます。

```
int x;
unsigned decltype(x); // C3554
```
