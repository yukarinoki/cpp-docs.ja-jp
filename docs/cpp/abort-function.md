---
title: abort 関数
ms.date: 12/01/2017
helpviewer_keywords:
- abort function
ms.assetid: 3352bcc4-1a8a-4e1f-8dcc-fe30f6b50f2d
ms.openlocfilehash: 7c87cb4fe7349a0d623c765c20e7e213a8454571
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385103"
---
# <a name="abort-function"></a>abort 関数

**abort** 関数（標準インクルードファイル \<stdlib.h> で宣言されている）はC++プログラムを終了させます。 `exit` と **abort** の違いは、`exit` はC++ランタイムの終了処理が行われる事を可能にする(グローバルオブジェクトのデストラクタが呼び出される) のに対して **abort** はプログラムを即座に終了します。 詳細については、*C ランタイム ライブラリ (CRT) リファレンス* の [abort](../c-runtime-library/reference/abort.md) を参照してください。

## <a name="see-also"></a>関連項目

[プログラムの終了](../cpp/program-termination.md)
