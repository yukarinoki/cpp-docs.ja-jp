---
title: リンカー ツールの警告 LNK4086 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4086
dev_langs:
- C++
helpviewer_keywords:
- LNK4086
ms.assetid: ea1eecbb-ba2c-41bb-9a4f-fa0808a4b92d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 21a2ee7660f0ad78d04f7edb191929296c8d47a9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46079233"
---
# <a name="linker-tools-warning-lnk4086"></a>リンカー ツールの警告 LNK4086

エントリ ポイント 'function' は 'number' バイトの引数を持つ _ _stdcall ではありません。イメージは動作しない可能性があります。

DLL のエントリ ポイントである必要があります`__stdcall`します。 使用して、関数を再コンパイルするか、 [/Gz](../../build/reference/gd-gr-gv-gz-calling-convention.md)オプションまたは指定`__stdcall`または WINAPI 関数を定義するときにします。