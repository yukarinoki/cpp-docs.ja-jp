---
title: 'オートメーション サーバー : オブジェクトの生成と破棄'
ms.date: 11/04/2016
helpviewer_keywords:
- objects [MFC], lifetime
- lifetime, automation server
- Automation servers, object lifetime
- servers, lifetime of Automation
ms.assetid: 342baacf-4015-4a0e-be2f-321424f1cb43
ms.openlocfilehash: 8031902318a091b0ed5f340b454a14b9df195069
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225086"
---
# <a name="automation-servers-object-lifetime-issues"></a>オートメーション サーバー : オブジェクトの生成と破棄

オートメーションクライアントが OLE 項目を作成またはアクティブ化すると、サーバーはそのオブジェクトへのポインターをクライアントに渡します。 クライアントは、OLE 関数[IUnknown:: AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref)を呼び出すことによって、オブジェクトへの参照を確立します。 この参照は、クライアントが[IUnknown:: Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release)を呼び出すまで有効です。 (Microsoft Foundation Class ライブラリの OLE クラスを使用して記述されたクライアントアプリケーションは、これらの呼び出しを行う必要はありません。フレームワークによって行われます)。OLE システムとサーバー自体がオブジェクトへの参照を確立する場合があります。 サーバーは、オブジェクトへの外部参照が有効な場合に限り、オブジェクトを破棄しないでください。

フレームワークは、 [CCmdTarget](reference/ccmdtarget-class.md)から派生したすべてのサーバーオブジェクトへの参照数の内部カウントを保持します。 この数は、オートメーションクライアントまたはその他のエンティティがオブジェクトへの参照を追加または解放したときに更新されます。

参照カウントが0になると、フレームワークは仮想関数の[CCmdTarget:: OnFinalRelease](reference/ccmdtarget-class.md#onfinalrelease)を呼び出します。 この関数の既定の実装では、演算子を呼び出して **`delete`** このオブジェクトを削除します。

Microsoft Foundation Class ライブラリには、外部クライアントがアプリケーションのオブジェクトを参照している場合に、アプリケーションの動作を制御するための追加機能が用意されています。 サーバーは、各オブジェクトへの参照の数を保持するだけでなく、アクティブなオブジェクトのグローバル数を保持します。 グローバル関数[afxolelockapp 呼び出し](reference/application-control.md#afxolelockapp)と[AfxOleUnlockApp](reference/application-control.md#afxoleunlockapp)は、アプリケーションのアクティブなオブジェクトの数を更新します。 このカウントが0以外の場合、ユーザーが [システム] メニューの [閉じる] を選択したとき、または [ファイル] メニューの [終了] を選択しても、アプリケーションは終了しません。 その代わり、保留中のすべてのクライアント要求が完了するまで、アプリケーションのメインウィンドウは非表示になります (破棄されません)。 通常、 `AfxOleLockApp` と `AfxOleUnlockApp` は、オートメーションをサポートするクラスのコンストラクターとデストラクターでそれぞれ呼び出されます。

場合によっては、クライアントがオブジェクトへの参照を保持している間に、サーバーが強制的に終了します。 たとえば、サーバーが依存しているリソースが使用できなくなり、サーバーでエラーが発生することがあります。 ユーザーは、他のアプリケーションが参照しているオブジェクトを含むサーバードキュメントを閉じることもできます。

Windows SDK については、「」および「」を参照してください `IUnknown::AddRef` `IUnknown::Release` 。

## <a name="see-also"></a>関連項目

[オートメーション サーバー](automation-servers.md)<br/>
[AfxOleCanExitApp](reference/application-control.md#afxolecanexitapp)
