---
title: リンカー ツールの警告 LNK4086
ms.date: 11/04/2016
f1_keywords:
- LNK4086
helpviewer_keywords:
- LNK4086
ms.assetid: ea1eecbb-ba2c-41bb-9a4f-fa0808a4b92d
ms.openlocfilehash: 6e012ceb5e20855353c69bbcde85fb78afad2011
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80183424"
---
# <a name="linker-tools-warning-lnk4086"></a>リンカー ツールの警告 LNK4086

entrypoint ' function ' は、引数の ' number ' バイトで __stdcall ません。イメージは実行されない可能性があります

DLL のエントリポイントを `__stdcall`する必要があります。 [/Gz](../../build/reference/gd-gr-gv-gz-calling-convention.md)オプションを使用して関数を再コンパイルするか、関数を定義するときに `__stdcall` または WINAPI を指定します。
