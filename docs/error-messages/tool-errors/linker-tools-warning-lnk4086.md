---
description: 詳細については、「リンカーツールの警告 LNK4086」を参照してください。
title: リンカー ツールの警告 LNK4086
ms.date: 11/04/2016
f1_keywords:
- LNK4086
helpviewer_keywords:
- LNK4086
ms.assetid: ea1eecbb-ba2c-41bb-9a4f-fa0808a4b92d
ms.openlocfilehash: f19138d895706579cff13bd1d43b9a64ccaa5044
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97210115"
---
# <a name="linker-tools-warning-lnk4086"></a>リンカー ツールの警告 LNK4086

entrypoint ' function ' は、引数の ' number ' バイトで __stdcall ません。イメージは実行されない可能性があります

DLL のエントリポイントはである必要があり **`__stdcall`** ます。 [/Gz](../../build/reference/gd-gr-gv-gz-calling-convention.md)オプションを使用して関数を再コンパイル **`__stdcall`** するか、関数を定義するときにまたは WINAPI を指定します。
