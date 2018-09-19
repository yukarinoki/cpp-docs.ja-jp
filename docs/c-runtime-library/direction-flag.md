---
title: 方向フラグ | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.flags
dev_langs:
- C++
helpviewer_keywords:
- direction flag
ms.assetid: 0836b4af-dbbb-4ab8-a4b2-156f2e2099e2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7db91b20b76ef06130cbb8357344352b820ed731
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46093204"
---
# <a name="direction-flag"></a>方向フラグ

方向フラグは、Intel 80x86 プロセッサ固有の CPU フラグです。 MOVS、MOVSD、MOVSW などの REP (繰り返し) プレフィックスを使用するすべてのアセンブリ命令に適用されます。 方向フラグがオフの場合、適用される命令に渡されたアドレスは増加します。

C ランタイム ルーチンでは、方向フラグがオフになっていることを前提としています。 C ランタイム関数とともに他の関数を使用している場合は、他の関数が方向フラグを変更しないようにする、または方向フラグを元の状態に復元する必要があります。 入力時に方向フラグがオフになっていると、ランタイム コードがより高速かつ効率的になります。

文字列操作ルーチンやバッファー操作ルーチンなどの C ランタイム ライブラリ関数では、方向フラグがオフになっていることを想定してあります。

## <a name="see-also"></a>参照

[CRT ライブラリの機能](../c-runtime-library/crt-library-features.md)