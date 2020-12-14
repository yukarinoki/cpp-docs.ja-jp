---
description: 詳細については、「標準コマンドとウィンドウ Id」を参照してください。
title: 標準コマンド ID とウィンドウ ID
ms.date: 11/04/2016
helpviewer_keywords:
- standard command and Window IDs
ms.assetid: 0424805c-fff8-4531-8f0c-15cfb13aa612
ms.openlocfilehash: 9f5a6b59d9451d749a48443bddf3560d2702bfe5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218902"
---
# <a name="standard-command-and-window-ids"></a>標準コマンド ID とウィンドウ ID

この Microsoft Foundation Class ライブラリでは、Afxres.h の標準コマンドとウィンドウ Id の数を定義します。 これらの Id は、リソースエディターおよび [クラスウィザード](mfc-class-wizard.md) でハンドラー関数にメッセージをマップするために最もよく使用されます。 すべての標準コマンドには、 **ID_** のプレフィックスが付いています。 たとえば、メニューエディターを使用する場合、通常は [ファイルを開く] メニュー項目を標準 ID_FILE_OPEN コマンド ID にバインドします。

ほとんどの標準コマンドでは、アプリケーションコードはコマンド ID を参照する必要がありません。これは、フレームワーク自体がプライマリフレームワーククラス (、、、など) のメッセージマップを使用してコマンドを処理するため `CWinThread` `CWinApp` `CView` `CDocument` です。

標準コマンド Id に加えて、 **AFX_ID** のプレフィックスを持つその他の多くの標準 id が定義されています。 これらの Id には、標準のウィンドウ Id (プレフィックス      **AFX_IDW_**)、文字列 id (プレフィックス **AFX_IDS_**)、および他のいくつかの型が含まれます。

**AFX_ID** プレフィックスで始まる id は、プログラマによって使用されることはほとんどありませんが、 **AFX_ID** s を参照するフレームワーク関数をオーバーライドする場合は、これらの id を参照する必要があります。

このリファレンスでは、Id は個別に記載されていません。 詳細については、「テクニカルノート [20](../../mfc/tn020-id-naming-and-numbering-conventions.md)、 [21](../../mfc/tn021-command-and-message-routing.md)、および [22](../../mfc/tn022-standard-commands-implementation.md)」を参照してください。

> [!NOTE]
> ヘッダーファイル Afxres.h は、間接的に Afxwin.h に含まれています。 アプリケーションのリソーススクリプト (.rc) ファイルには、次のステートメントを明示的に含める必要があります。

[!code-cpp[NVC_MFC_Utilities#47](../../mfc/codesnippet/cpp/standard-command-and-window-ids_1.h)]

## <a name="see-also"></a>関連項目

[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
