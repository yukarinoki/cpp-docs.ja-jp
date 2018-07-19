---
title: リンカー ツールの警告 LNK4086 |Microsoft ドキュメント
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
ms.openlocfilehash: b7b3ad3a8ceebf97ccdcf7a1d8079886f54a3984
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33301162"
---
# <a name="linker-tools-warning-lnk4086"></a>リンカー ツールの警告 LNK4086
entrypoint 'function' は 'number' バイトの引数を持つ _ _stdcall ではありません。イメージは動作しない可能性があります。  
  
 DLL のエントリ ポイントがある必要があります`__stdcall`です。 持つ関数が再コンパイルするか、 [/Gz](../../build/reference/gd-gr-gv-gz-calling-convention.md)オプションを指定するか`__stdcall`または WINAPI 関数を定義するとします。