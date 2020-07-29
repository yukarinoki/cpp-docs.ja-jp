---
title: リンカー ツールの警告 LNK4086
ms.date: 11/04/2016
f1_keywords:
- LNK4086
helpviewer_keywords:
- LNK4086
ms.assetid: ea1eecbb-ba2c-41bb-9a4f-fa0808a4b92d
ms.openlocfilehash: f692f848825cd3d8e5e1fc042cb94d7cce8ea6bf
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87195812"
---
# <a name="linker-tools-warning-lnk4086"></a>リンカー ツールの警告 LNK4086

entrypoint ' function ' は、引数の ' number ' バイトで __stdcall ません。イメージは実行されない可能性があります

DLL のエントリポイントはである必要があり **`__stdcall`** ます。 [/Gz](../../build/reference/gd-gr-gv-gz-calling-convention.md)オプションを使用して関数を再コンパイル **`__stdcall`** するか、関数を定義するときにまたは WINAPI を指定します。
