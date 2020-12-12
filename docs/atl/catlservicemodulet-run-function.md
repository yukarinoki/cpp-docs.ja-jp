---
description: '詳細について: CAtlServiceModuleT:: Run 関数'
title: 'CAtlServiceModuleT:: Run 関数'
ms.date: 11/04/2016
helpviewer_keywords:
- ATL services, security
ms.assetid: 42c010f0-e60e-459c-a63b-a53a24cda93b
ms.openlocfilehash: f8bba170236138f6491c49506bccd29bc23d9dec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148344"
---
# <a name="catlservicemoduletrun-function"></a>CAtlServiceModuleT:: Run 関数

`Run` 、、およびへの呼び出しが含まれてい `PreMessageLoop` `RunMessageLoop` `PostMessageLoop` ます。 を呼び出すと、 `PreMessageLoop` 最初にサービスのスレッド ID が格納されます。 サービスは、この ID を使用して、Win32 API 関数の [Postthreadmessage](/windows/win32/api/winuser/nf-winuser-postthreadmessagew)を使用して WM_QUIT メッセージを送信することによって、メッセージを閉じます。

`PreMessageLoop` 次に、を呼び出し `InitializeSecurity` ます。 既定では、は、 `InitializeSecurity` セキュリティ記述子が NULL に設定された [CoInitializeSecurity](/windows/win32/api/combaseapi/nf-combaseapi-coinitializesecurity) を呼び出します。これは、すべてのユーザーがオブジェクトにアクセスできることを意味します。

サービスで独自のセキュリティを指定しない場合は `PreMessageLoop` 、をオーバーライドし、を呼び出さないでください。これにより `InitializeSecurity` 、COM はレジストリからセキュリティ設定を決定します。 レジストリ設定を構成する便利な方法は、このセクションで後述する [DCOMCNFG](../atl/dcomcnfg.md) ユーティリティを使用することです。

セキュリティを指定すると、オブジェクトは COM に登録され、新しいクライアントがプログラムに接続できるようになります。 最後に、プログラムは、実行されていることをサービスコントロールマネージャー (SCM) に伝え、プログラムはメッセージループに入ります。 サービスのシャットダウン時に終了メッセージをポストするまで、プログラムは実行されたままになります。

## <a name="see-also"></a>関連項目

[サービス](../atl/atl-services.md)<br/>
[CSecurityDesc クラス](../atl/reference/csecuritydesc-class.md)<br/>
[CSid クラス](../atl/reference/csid-class.md)<br/>
[CDacl クラス](../atl/reference/cdacl-class.md)<br/>
[CAtlServiceModuleT:: Run](../atl/reference/catlservicemodulet-class.md#run)
