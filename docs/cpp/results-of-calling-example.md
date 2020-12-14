---
description: '詳細情報: 呼び出し例の結果'
title: サンプル呼び出しの結果
ms.date: 11/19/2018
helpviewer_keywords:
- examples [C++], results of calling
- results, thiscall call
- results, __fastcall keyword call
- results, __cdecl call
- results, __stdcall call
ms.assetid: aa70a7cb-ba1d-4aa6-bd0a-ba783da2e642
ms.openlocfilehash: 91da3182742414dc4850013463b74ae36aa782c0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97262920"
---
# <a name="results-of-calling-example"></a>サンプル呼び出しの結果

**Microsoft 固有の仕様**

## <a name="__cdecl"></a>__cdecl

C の修飾された関数名は `_MyFunc` です。

![CDECL 呼び出し規則](../cpp/media/vc37i01.gif "CDECL 呼び出し規則") <br/>
**`__cdecl`** 呼び出し規約

## <a name="__stdcall-and-thiscall"></a>__stdcall と thiscall

C の装飾名 ( **`__stdcall`** ) は `_MyFunc@20` です。 C++ の装飾名は実装固有です。

![&#95;&#95;stdcall と thiscall の呼び出し規約](../cpp/media/vc37i02.gif "&#95;&#95;stdcall と thiscall の呼び出し規約") <br/>
__stdcall と thiscall の呼び出し規約

## <a name="__fastcall"></a>__fastcall

C の装飾名 ( **`__fastcall`** ) は `@MyFunc@20` です。 C++ の装飾名は実装固有です。

![ &#95;&#95;fastcall の呼び出し規約](../cpp/media/vc37i03.gif " &#95;&#95;fastcall の呼び出し規約") <br/>
__fastcall の呼び出し規則

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[呼び出しの例: 関数プロトタイプと呼び出し](../cpp/calling-example-function-prototype-and-call.md)
