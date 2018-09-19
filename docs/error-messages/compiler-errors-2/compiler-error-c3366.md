---
title: コンパイラ エラー C3366 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3366
dev_langs:
- C++
helpviewer_keywords:
- C3366
ms.assetid: efc55bcf-c16d-43c1-a36f-87a6165fa2a8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b3638ba2415839c044d9a82d82d0abe8bc2c98e2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46026505"
---
# <a name="compiler-error-c3366"></a>コンパイラ エラー C3366

'variable': 静的データ メンバーの管理または WinRTtypes をクラス定義内で定義する必要があります

WinRT または .NET のクラスまたはインターフェイスの静的メンバーをそのクラスまたはインターフェイスの定義外で参照しようとしました。

コンパイラは、(1 回のパスの後に、メタデータを出力するために) クラスの完全定義を認識する必要があり、静的データ メンバーをクラス内で初期化する必要があります。

たとえば、次の例では、C3366 を生成し、その修正方法を示しています。

```
// C3366.cpp
// compile with: /clr /c
ref class X {
   public:
   static int i;   // initialize i here to avoid C3366
};

int X::i = 5;      // C3366
```
