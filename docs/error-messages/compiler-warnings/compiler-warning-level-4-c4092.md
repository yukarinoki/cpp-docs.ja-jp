---
title: コンパイラの警告 (レベル 4) C4092
ms.date: 11/04/2016
f1_keywords:
- C4092
helpviewer_keywords:
- C4092
ms.assetid: 396ae826-a892-4327-bd66-f4762376d72b
ms.openlocfilehash: 6786d692785dbca575d4b241b7b3e3d40575b686
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198550"
---
# <a name="compiler-warning-level-4-c4092"></a>コンパイラの警告 (レベル 4) C4092

sizeof は ' unsigned long ' を返します

`sizeof` 演算子のオペランドが非常に大きいため、`sizeof` は unsigned **long**を返しました。 この警告は、Microsoft 拡張機能 ([/ze](../../build/reference/za-ze-disable-language-extensions.md)) で発生します。 ANSI 互換 (/Za) では、代わりに結果が切り捨てられます。
