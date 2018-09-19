---
title: 制御フラグ | Microsoft Docs
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
- flags, control
- heap allocation, control flags
- debug heap, control flags
ms.assetid: 8dbd24a5-0633-42d1-9771-776db338465f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 716e597be5d337d11d58df944bbba468e496f078
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46078063"
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