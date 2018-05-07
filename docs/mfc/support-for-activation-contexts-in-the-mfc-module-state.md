---
title: MFC モジュール状態でのアクティベーション コンテキスト サポート |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- activation contexts [MFC]
- activation contexts [MFC], MFC support
ms.assetid: 1e49eea9-3620-46dd-bc5f-d664749567c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2713e0025c0587a4ab76813d4d07eed0825db447
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="support-for-activation-contexts-in-the-mfc-module-state"></a>MFC モジュール状態でのアクティベーション コンテキストのサポート
MFC では、ユーザー モジュールによって指定されたマニフェスト リソースを使用してアクティブ化コンテキストを作成します。 アクティベーションのコンテキストを作成する方法の詳細については、次のトピックを参照してください。  
  
-   [アクティベーションのコンテキスト](http://msdn.microsoft.com/library/aa374153)  
  
-   [アプリケーション マニフェスト](http://msdn.microsoft.com/library/aa374191)  
  
-   [アセンブリ マニフェスト](http://msdn.microsoft.com/library/aa374219)  
  
## <a name="remarks"></a>コメント  
 これらの Windows SDK のトピックを読むと、MFC は Windows SDK のアクティブ化コンテキストの API を使用していないことを除いて、MFC のアクティブ化コンテキストのメカニズムの Windows SDK のアクティベーション コンテキストようなものを確認します。  
  
 アクティブ化コンテキストは、次のように、MFC アプリケーション、Dll のユーザー、および MFC 拡張 Dll で動作します。  
  
-   MFC アプリケーションでは、自身のマニフェスト リソースのリソース ID 1 を使用します。 この場合、MFC は、それぞれのアクティブ化コンテキストを作成しませんが、既定のアプリケーション コンテキストを使用します。  
  
-   MFC ユーザー Dll は、自身のマニフェスト リソースのリソース ID が 2 を使用します。 ここでは、MFC は、別のユーザーの Dll が別のバージョンの同じライブラリ (コモン コントロール ライブラリなど) を使用できるように、各ユーザー DLL のアクティベーション コンテキストを作成します。  
  
-   MFC 拡張 Dll は、ホスト アプリケーションやユーザーに Dll がアクティブ化コンテキストを確立するために依存しています。  
  
 説明されているプロセスを使用してアクティブ化コンテキストの状態を変更することができますが[アクティブ化コンテキストの API を使用して](http://msdn.microsoft.com/library/aa376620)MFC のアクティベーション コンテキストのメカニズムを使用する場合に利用できプラグイン アーキテクチャの DLL ベースの開発ここでは簡単な (またはできません) 外部プラグインに個々 の呼び出しの前後に手動でアクティブ化の状態を切り替える。  
  
 アクティブ化コンテキストは[AfxWinInit](../mfc/reference/application-information-and-management.md#afxwininit)です。 破棄は、`AFX_MODULE_STATE`デストラクターです。 アクティブ化コンテキスト ハンドルが保持される`AFX_MODULE_STATE`です。 (`AFX_MODULE_STATE`は、「 [AfxGetStaticModuleState](reference/extension-dll-macros.md#afxgetstaticmodulestate)。)  
  
 [AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state)マクロがアクティブにし、アクティベーション コンテキストが非アクティブ化します。 `AFX_MANAGE_STATE` ユーザーの DLL によって選択されている適切なアクティベーション コンテキストで実行する MFC コードを許可する MFC のスタティック ライブラリと MFC Dll の場合は、有効です。  
  
## <a name="see-also"></a>関連項目  
 [アクティベーションのコンテキスト](http://msdn.microsoft.com/library/aa374153)   
 [アプリケーション マニフェスト](http://msdn.microsoft.com/library/aa374191)   
 [アセンブリ マニフェスト](http://msdn.microsoft.com/library/aa374219)   
 [AfxWinInit](../mfc/reference/application-information-and-management.md#afxwininit)   
 [AfxGetStaticModuleState](reference/extension-dll-macros.md#afxgetstaticmodulestate)   
 [AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state)

