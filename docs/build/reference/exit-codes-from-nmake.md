---
title: NMAKE で返される終了コード
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, exit codes
- exit codes
ms.assetid: 75f6913c-1da5-4572-a2d3-8a4e058bed15
ms.openlocfilehash: 25ea4060e7b7a968b6a9da78f344e645c5d43a44
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57826389"
---
# <a name="exit-codes-from-nmake"></a>NMAKE で返される終了コード

NMAKE では、次の終了コードが返されます。

|コード|説明|
|----------|-------------|
|0|エラー (場合によっては警告)|
|1|(/K を使用する場合にのみを発行する) 不完全なビルド|
|2|プログラム エラー: 次のいずれかの原因として考えられます。|
||-メイクファイルに構文エラー|
||-コマンドからのエラーまたは終了コード|
||-ユーザーにより中断|
|4|システム エラー: メモリ不足|
|255|ターゲットが最新でない (/Q を使用する場合にのみ発行)|

## <a name="see-also"></a>関連項目

[NMAKE の実行](running-nmake.md)
