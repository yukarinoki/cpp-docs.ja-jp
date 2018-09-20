---
title: インクルード ファイルのマルチ スレッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- threading [C++], include files
- include files, multithreading
- multithreading [C++], include files
ms.assetid: 98d764f9-71f4-4da5-8f3a-8d2d26e96799
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 64ba6ec639151ca659e3bd075f691176ef4edbdd
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46422325"
---
# <a name="include-files-for-multithreading"></a>マルチスレッドのためのインクルード ファイル

標準のインクルード ファイル、ライブラリで実装された、C ランタイム ライブラリ関数を宣言します。 使用する場合、[最大限の最適化](../build/reference/ox-full-optimization.md)(/Ox) または[fastcall 呼び出し規約](../build/reference/gd-gr-gv-gz-calling-convention.md)(/Gr) オプションでは、コンパイラは、register 呼び出し規約を使用してすべての関数を呼び出します。 ランタイム ライブラリ関数が C の呼び出し規則を使用してコンパイルされたし、標準のインクルード ファイル内の宣言がこれらの関数の適切な外部参照を生成するようにコンパイラに指示します。

## <a name="see-also"></a>関連項目

[C と Win32 を使用するマルチスレッド](multithreading-with-c-and-win32.md)