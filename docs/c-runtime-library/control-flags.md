---
title: 制御フラグ
ms.date: 11/04/2016
f1_keywords:
- c.flags
helpviewer_keywords:
- flags, control
- heap allocation, control flags
- debug heap, control flags
ms.assetid: 8dbd24a5-0633-42d1-9771-776db338465f
ms.openlocfilehash: 45349099ed5c607468430d2f0a901c6374d88fc7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50475739"
---
# <a name="control-flags"></a>制御フラグ

Microsoft C ランタイム ライブラリのデバッグ バージョンは次のフラグを使用し、ヒープ割り当てとレポート プロセスを制御します。 詳細については、「[CRT のデバッグ技術](/visualstudio/debugger/crt-debugging-techniques)」を参照してください。

|フラグ|説明|
|----------|-----------------|
|[_CRTDBG_MAP_ALLOC](../c-runtime-library/crtdbg-map-alloc.md)|基本のヒープ関数をデバッグ バージョンのそれにマッピングする|
|[_DEBUG](../c-runtime-library/debug.md)|ランタイム関数のデバッグ バージョンの使用を有効にする|
|[_crtDbgFlag](../c-runtime-library/crtdbgflag.md)|デバッグ ヒープ マネージャーの割り当て追跡記録方法を制御する|

これらのフラグは、/D コマンドライン オプションまたは `#define` ディレクティブで定義できます。 フラグが `#define` で定義されるとき、ルーチン宣言のヘッダー ファイル インクルード ステートメントの前にディレクティブが現れるはずです。

## <a name="see-also"></a>参照

[グローバル変数および基本データ型](../c-runtime-library/global-variables-and-standard-types.md)