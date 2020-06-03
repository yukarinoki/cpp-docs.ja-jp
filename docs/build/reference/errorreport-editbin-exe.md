---
title: /ERRORREPORT (editbin.exe)
description: Microsoft EDITBIN ユーティリティ/ERRORREPORT コマンドラインオプションのリファレンスです。
ms.date: 02/09/2020
f1_keywords:
- /ERRORREPORT_editbin
helpviewer_keywords:
- -ERRORREPORT editbin option
- ERRORREPORT editbin option
- /ERRORREPORT editbin option
ms.assetid: eca66ac3-b754-4bd7-9dd4-e04fc79a71b6
ms.openlocfilehash: 4456a49cc53b21bd24c616852159ca299181071b
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79439905"
---
# <a name="errorreport-editbinexe"></a>/ERRORREPORT (editbin.exe)

> [!NOTE]
> /ERRORREPORT オプションは非推奨とされます。 Windows Vista 以降では、エラー報告は[Windows エラー報告 (WER)](/windows/win32/wer/windows-error-reporting)設定によって制御されます。

## <a name="syntax"></a>構文

> **/Errorreport** \[ **NONE** \| **PROMPT** \| **QUEUE** \| **SEND** ]

## <a name="remarks"></a>コメント

**/Errorreport**引数は、Windows エラー報告サービスの設定によってオーバーライドされます。 EDITBIN では、レポートが Windows エラー報告によって有効になっている場合、内部エラーのレポートが Microsoft に自動的に送信されます。 Windows エラー報告で無効になっている場合、レポートは送信されません。

## <a name="see-also"></a>参照

[EDITBIN オプション](editbin-options.md)
