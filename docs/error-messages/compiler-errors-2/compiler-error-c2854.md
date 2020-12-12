---
description: 詳細については、「コンパイラエラー C2854」を参照してください。
title: コンパイラ エラー C2854
ms.date: 11/04/2016
f1_keywords:
- C2854
helpviewer_keywords:
- C2854
ms.assetid: 917fec9c-790a-4149-8dfc-00d17a09199c
ms.openlocfilehash: beb4947e365d1a64d5b0c8ad5ffcdf647b0939d0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97260138"
---
# <a name="compiler-error-c2854"></a>コンパイラ エラー C2854

#pragma hdrstop に構文エラーがあります

に `#pragma hdrstop` 無効なファイル名が与えられています。 プラグマの後に、省略可能なファイル名をかっこと引用符で囲んで指定できます。

次の例では、C2854 が生成されます。

```cpp
// C2854.cpp
// compile with: /c
#pragma hdrstop( "\\source\\pchfiles\\myheader.pch" ]   // C2854
// try the following line instead
// #pragma hdrstop( "\\source\\pchfiles\\myheader.pch" )
```
