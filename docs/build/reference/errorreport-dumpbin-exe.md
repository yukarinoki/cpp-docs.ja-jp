---
title: /ERRORREPORT (dumpbin.exe)
description: Microsoft DUMPBIN ユーティリティ/ERRORREPORT コマンドラインオプションのリファレンスです。
ms.date: 02/09/2020
f1_keywords:
- /ERRORREPORT_dumpbin
helpviewer_keywords:
- -ERRORREPORT dumpbin option
- ERRORREPORT dumpbin option
- /ERRORREPORT dumpbin option
ms.assetid: 51178c43-4f95-4fda-8f97-50a257d1c948
ms.openlocfilehash: f701c2e28dcf82194589877709bf6959de4bcbfc
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79439935"
---
# <a name="errorreport-dumpbinexe"></a>/ERRORREPORT (dumpbin.exe)

> [!NOTE]
> /ERRORREPORT オプションは非推奨とされます。 Windows Vista 以降では、エラー報告は[Windows エラー報告 (WER)](/windows/win32/wer/windows-error-reporting)設定によって制御されます。

## <a name="syntax"></a>構文

> **/Errorreport**\[**NONE** \| **PROMPT** \| **QUEUE** \| **SEND** ]

## <a name="remarks"></a>コメント

**/Errorreport**引数は、Windows エラー報告サービスの設定によってオーバーライドされます。 レポートが Windows エラー報告によって有効になっている場合、DUMPBIN によって内部エラーのレポートが Microsoft に自動的に送信されます。 Windows エラー報告で無効になっている場合、レポートは送信されません。

## <a name="see-also"></a>参照

[DUMPBIN オプション](dumpbin-options.md)
