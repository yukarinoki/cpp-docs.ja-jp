---
title: コンパイラ エラー C3917 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3917
dev_langs:
- C++
helpviewer_keywords:
- C3917
ms.assetid: a24cd0c9-262f-46e5-9488-1c01f945933d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3c98141d07bbe7d1990434d2a46f116a266be1c0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46072694"
---
# <a name="compiler-error-c3917"></a>コンパイラ エラー C3917

'*プロパティ*': コンス トラクターの宣言スタイル

プロパティまたはイベント定義では、Visual Studio 2005 より前に、のバージョンの構文を使用します。

詳細については、「 [property](../../windows/property-cpp-component-extensions.md)」を参照してください。

## <a name="example"></a>例

```cpp
// C3917.cpp
// compile with: /clr /c
public ref class  C {
private:
   int m_length;
public:
   C() {
      m_length = 0;
   }

   property int get_Length();   // C3917

   // The correct property definition:
   property int Length {
      int get() {
         return m_length;
      }

      void set( int i ) {
         m_length = i;
      }
   }
};
```