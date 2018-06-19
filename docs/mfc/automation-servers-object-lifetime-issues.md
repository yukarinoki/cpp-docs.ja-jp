---
title: 'オートメーション サーバー: オブジェクトの有効期間に関する問題 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- objects [MFC], lifetime
- lifetime, automation server
- Automation servers, object lifetime
- servers, lifetime of Automation
ms.assetid: 342baacf-4015-4a0e-be2f-321424f1cb43
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e27812c20a64f5472c29a66298bcdec30bf4ef2b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33341801"
---
# <a name="automation-servers-object-lifetime-issues"></a>オートメーション サーバー : オブジェクトの生成と破棄
オートメーション クライアントは、作成または OLE 項目をアクティブ化、ときに、サーバー、クライアントにポインターを渡しますそのオブジェクト。 クライアントが OLE 関数を呼び出すことによって、オブジェクトへの参照を確立[:addref](http://msdn.microsoft.com/library/windows/desktop/ms691379)です。 この参照が有効でクライアントの呼び出しまで[iunknown::release](http://msdn.microsoft.com/library/windows/desktop/ms682317)です。 (Microsoft Foundation Class ライブラリの OLE クラスで記述されたクライアント アプリケーションでは、これらの呼び出しをする必要がなくなります。 は、フレームワークです。)OLE システムと、サーバー自体は、オブジェクトへの参照を確立可能性があります。 オブジェクトへの外部参照が有効に残っている限り、サーバーはオブジェクトを破棄できません。  
  
 フレームワークから派生した任意のサーバー オブジェクトへの参照の数の内部でカウントを保持する[CCmdTarget](../mfc/reference/ccmdtarget-class.md)です。 オートメーション クライアントの場合に、カウントが更新またはその他のエンティティを追加またはオブジェクトへの参照を解放します。  
  
 フレームワークが仮想関数を呼び出す、参照カウントが 0 になったら、 [CCmdTarget::OnFinalRelease](../mfc/reference/ccmdtarget-class.md#onfinalrelease)です。 この関数の既定の実装、**削除**演算子をこのオブジェクトを削除します。  
  
 Microsoft Foundation Class ライブラリでは、外部クライアント アプリケーションのオブジェクトへの参照がある場合は、アプリケーションの動作を制御するための他の機能を提供します。 各オブジェクトへの参照カウントを維持するには、以外は、サーバーは、アクティブなオブジェクトのグローバルなカウントを保持します。 グローバル関数[AfxOleLockApp](../mfc/reference/application-control.md#afxolelockapp)と[AfxOleUnlockApp](../mfc/reference/application-control.md#afxoleunlockapp)アクティブなオブジェクトのアプリケーションの数を更新します。 この数が 0 以外の場合は、アプリケーションをユーザーがシステム メニューまたは [ファイル] メニューからの終了から閉じるを選択したときに終了しません。 代わりに、アプリケーションのメイン ウィンドウが非表示には破棄されません) まですべてのクライアント要求が完了して保留中です。 通常、`AfxOleLockApp`と`AfxOleUnlockApp`オートメーションをサポートするクラスのそれぞれに、コンス トラクターとデストラクターで呼び出されます。  
  
 場合もあります状況は、サーバーをクライアントがまだオブジェクトへの参照中に終了を強制します。 たとえば、サーバーが依存するリソースできない可能性があります、サーバー エラーが発生する原因とします。 ユーザーは、他のアプリケーションを参照しているオブジェクトを含むサーバー ドキュメントを閉じるも可能性があります。  
  
 Windows SDK を参照してください。`IUnknown::AddRef`と`IUnknown::Release`です。  
  
## <a name="see-also"></a>関連項目  
 [オートメーション サーバー](../mfc/automation-servers.md)   
 [AfxOleCanExitApp](../mfc/reference/application-control.md#afxolecanexitapp)

