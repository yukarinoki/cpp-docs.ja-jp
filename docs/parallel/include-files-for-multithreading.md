---
title: マルチスレッドのためのインクルード ファイル
ms.date: 11/04/2016
helpviewer_keywords:
- threading [C++], include files
- include files, multithreading
- multithreading [C++], include files
ms.assetid: 98d764f9-71f4-4da5-8f3a-8d2d26e96799
ms.openlocfilehash: 79b5c56eecfaf28743eec4ba6b4cee56156d6e2c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62212897"
---
# <a name="include-files-for-multithreading"></a>マルチスレッドのためのインクルード ファイル

標準のインクルード ファイル、ライブラリで実装された、C ランタイム ライブラリ関数を宣言します。 使用する場合、[最大限の最適化](../build/reference/ox-full-optimization.md)(/Ox) または[fastcall 呼び出し規約](../build/reference/gd-gr-gv-gz-calling-convention.md)(/Gr) オプションでは、コンパイラは、register 呼び出し規約を使用してすべての関数を呼び出します。 ランタイム ライブラリ関数が C の呼び出し規則を使用してコンパイルされたし、標準のインクルード ファイル内の宣言がこれらの関数の適切な外部参照を生成するようにコンパイラに指示します。

## <a name="see-also"></a>関連項目

[C と Win32 を使用するマルチスレッド](multithreading-with-c-and-win32.md)
