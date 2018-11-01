---
title: サンプル呼び出しの結果
ms.date: 09/05/2018
helpviewer_keywords:
- examples [C++], results of calling
- results, thiscall call
- results, __fastcall keyword call
- results, __cdecl call
- results, __stdcall call
ms.assetid: aa70a7cb-ba1d-4aa6-bd0a-ba783da2e642
ms.openlocfilehash: 96582e48912bb591d869bbc4df179299e6459f1e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50500940"
---
# <a name="results-of-calling-example"></a>サンプル呼び出しの結果

**Microsoft 固有の仕様**

## <a name="cdecl"></a>__cdecl

C の装飾関数名は`_MyFunc`します。

![CDECL 呼び出し規約](../cpp/media/vc37i01.gif "vc37I01") 、 **_ _cdecl**呼び出し規約

## <a name="stdcall-and-thiscall"></a>__stdcall と thiscall

C の装飾名 (**_ _stdcall**) は`_MyFunc@20`します。 C++ の装飾名は、実装に固有です。

![&#95;&#95;stdcall と thiscall の呼び出し規約](../cpp/media/vc37i02.gif "vc37I02") _ _stdcall と thiscall の呼び出し規則

## <a name="fastcall"></a>__fastcall

C の装飾名 (**_ _fastcall**) は`@MyFunc@20`します。 C++ の装飾名は、実装に固有です。

![呼び出し規約の&#95; &#95;fastcall](../cpp/media/vc37i03.gif "vc37I03") _ _fastcall 呼び出し規約

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[呼び出しの例: 関数プロトタイプと呼び出し](../cpp/calling-example-function-prototype-and-call.md)