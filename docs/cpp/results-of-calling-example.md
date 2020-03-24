---
title: サンプル呼び出しの結果
ms.date: 11/19/2018
helpviewer_keywords:
- examples [C++], results of calling
- results, thiscall call
- results, __fastcall keyword call
- results, __cdecl call
- results, __stdcall call
ms.assetid: aa70a7cb-ba1d-4aa6-bd0a-ba783da2e642
ms.openlocfilehash: edbeb187e568b833673d91ef70ff57fbd460659c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80179056"
---
# <a name="results-of-calling-example"></a>サンプル呼び出しの結果

**Microsoft 固有の仕様**

## <a name="__cdecl"></a>__cdecl

C の修飾された関数名が `_MyFunc`。

![CDECL 呼び出し規約](../cpp/media/vc37i01.gif "CDECL 呼び出し規約") <br/>
**__Cdecl**呼び出し規約

## <a name="__stdcall-and-thiscall"></a>__stdcall と thiscall

C の装飾名 ( **__stdcall**) は `_MyFunc@20`。 C++装飾名は実装固有です。

![&#95;&#95;stdcall と thiscall の呼び出し規約](../cpp/media/vc37i02.gif "&#95;&#95;stdcall と thiscall の呼び出し規約") <br/>
__stdcall と thiscall の呼び出し規約

## <a name="__fastcall"></a>__fastcall

C の装飾名 ( **__fastcall**) は `@MyFunc@20`。 C++装飾名は実装固有です。

![Fastcall の&#95; &#95;呼び出し規約](../cpp/media/vc37i03.gif "Fastcall の&#95; &#95;呼び出し規約") <br/>
__fastcall の呼び出し規則

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[呼び出しの例: 関数プロトタイプと呼び出し](../cpp/calling-example-function-prototype-and-call.md)
