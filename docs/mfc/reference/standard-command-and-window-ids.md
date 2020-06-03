---
title: 標準コマンド ID とウィンドウ ID
ms.date: 11/04/2016
helpviewer_keywords:
- standard command and Window IDs
ms.assetid: 0424805c-fff8-4531-8f0c-15cfb13aa612
ms.openlocfilehash: a7f9e37702c686e13379d4034be94949f92e5e79
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372954"
---
# <a name="standard-command-and-window-ids"></a>標準コマンド ID とウィンドウ ID

Microsoft ファウンデーション クラス ライブラリでは、Afxres.h で多くの標準コマンド ID とウィンドウ ID を定義しています。 これらの ID は、リソース エディターおよび[クラス ウィザード](mfc-class-wizard.md)内で最も一般的に使用され、メッセージをハンドラー関数にマップします。 すべての標準コマンドには **、ID_** プレフィックスがあります。 たとえば、メニュー エディタを使用する場合、通常は[ファイルを開く]メニュー項目を標準のID_FILE_OPENコマンド ID にバインドします。

ほとんどの標準`CWinThread`コマンドでは、フレームワーク自体がプライマリ フレームワーク クラス (、、、、`CWinApp``CView`など`CDocument`) でメッセージ マップを介してコマンドを処理するため、アプリケーション コードはコマンド ID を参照する必要はありません。

標準コマンド ID に加えて、AFX_ID の接頭辞を持つ他の多くの標準 ID が定義**されています。** これらの ID には、標準ウィンドウ ID (プレフィックス**AFX_IDW_)、** 文字列 ID **(AFX_IDS_** プレフィックス) などがあります。

**AFX_ID**プレフィックスで始まる ID はプログラマによってほとんど使用されませんが **、AFX_ID**を参照するフレームワーク関数をオーバーライドする場合は、これらの ID を参照する必要があります。

ID は、このリファレンスで個別に文書化されていません。 詳細については、テクニカル ノート[20、](../../mfc/tn020-id-naming-and-numbering-conventions.md) [21](../../mfc/tn021-command-and-message-routing.md)、および[22](../../mfc/tn022-standard-commands-implementation.md)を参照してください。

> [!NOTE]
> ヘッダー ファイル Afxres.h は間接的に Afxwin.h に含まれています。 アプリケーションのリソース スクリプト (.rc) ファイルには、次のステートメントを明示的に含める必要があります。

[!code-cpp[NVC_MFC_Utilities#47](../../mfc/codesnippet/cpp/standard-command-and-window-ids_1.h)]

## <a name="see-also"></a>関連項目

[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
