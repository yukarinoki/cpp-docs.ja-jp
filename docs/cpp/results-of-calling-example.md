---
title: サンプル呼び出しの結果 |Microsoft Docs
ms.custom: ''
ms.date: 09/05/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- examples [C++], results of calling
- results, thiscall call
- results, __fastcall keyword call
- results, __cdecl call
- results, __stdcall call
ms.assetid: aa70a7cb-ba1d-4aa6-bd0a-ba783da2e642
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5687adfada8657ae26edd9001db8990ff08864e9
ms.sourcegitcommit: d10a2382832373b900b1780e1190ab104175397f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2018
ms.locfileid: "43894696"
---
# <a name="results-of-calling-example"></a>サンプル呼び出しの結果

**Microsoft 固有の仕様**

## <a name="cdecl"></a>__cdecl
C の装飾関数名は`_MyFunc`します。

![CDECL 呼び出し規約](../cpp/media/vc37i01.gif "vc37I01")  
**_ _Cdecl**呼び出し規約

## <a name="stdcall-and-thiscall"></a>__stdcall と thiscall

C の装飾名 (**_ _stdcall**) は`_MyFunc@20`します。 C++ の装飾名は、実装に固有です。

![&#95;&#95;stdcall と thiscall の呼び出し規約](../cpp/media/vc37i02.gif "vc37I02")  
__stdcall と thiscall の呼び出し規則

## <a name="fastcall"></a>__fastcall

C の装飾名 (**_ _fastcall**) は`@MyFunc@20`します。 C++ の装飾名は、実装に固有です。

![呼び出し規約の&#95; &#95;fastcall](../cpp/media/vc37i03.gif "vc37I03")  
__fastcall の呼び出し規則

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[呼び出しの例: 関数プロトタイプと呼び出し](../cpp/calling-example-function-prototype-and-call.md)