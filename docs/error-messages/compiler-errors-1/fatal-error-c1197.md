---
description: '詳細情報: 致命的なエラー C1197'
title: 致命的なエラー C1197
ms.date: 11/04/2016
f1_keywords:
- C1197
helpviewer_keywords:
- C1197
ms.assetid: 22b801b7-e792-41f6-a461-973c03c69f25
ms.openlocfilehash: c61cbd71fa8f17dc787fd9ee5eabd0f073aafb39
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97268172"
---
# <a name="fatal-error-c1197"></a>致命的なエラー C1197

' mscorlib.dll_1 ' を参照できません。プログラムは ' mscorlib.dll_2 ' を既に参照しています。

コンパイラは、共通言語ランタイムのバージョンと一致します。  ただし、以前のバージョンから共通言語ランタイムファイルのバージョンを参照しようとしました。

このエラーを解決するには、コンパイルするバージョンの Visual C++ に付属している共通言語ランタイムのバージョンのファイルのみを参照します。

## <a name="example"></a>例

次の例では、C1197 が生成されます。

```cpp
// C1197.cpp
// compile with: /clr /c
// processor: x86
#using "C:\Windows\Microsoft.NET\Framework\v1.1.4322\mscorlib.dll"   // C1197
// try the following line instead
// #using "mscorlib.dll"
```
