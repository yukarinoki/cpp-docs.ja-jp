---
title: MFC モジュール状態でのアクティベーション コンテキストのサポート
ms.date: 11/04/2016
helpviewer_keywords:
- activation contexts [MFC]
- activation contexts [MFC], MFC support
ms.assetid: 1e49eea9-3620-46dd-bc5f-d664749567c7
ms.openlocfilehash: a2e5f56eeb323f1bd5f20c5920bbdbe4a658554d
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57267863"
---
# <a name="support-for-activation-contexts-in-the-mfc-module-state"></a>MFC モジュール状態でのアクティベーション コンテキストのサポート

MFC では、ユーザーのモジュールによって得られるマニフェスト リソースを使用してアクティブ化コンテキストを作成します。 アクティベーション コンテキストを作成する方法の詳細については、次のトピックを参照してください。

- [アクティベーション コンテキスト](/windows/desktop/SbsCs/activation-contexts)

- [アプリケーション マニフェスト](/windows/desktop/SbsCs/application-manifests)

- [アセンブリ マニフェスト](/windows/desktop/SbsCs/assembly-manifests)

## <a name="remarks"></a>Remarks

これらの Windows SDK のトピックを読むときは、MFC は Windows SDK のアクティブ化コンテキストの API を使用しないことを除いて、MFC のアクティベーション コンテキストのメカニズムは Windows SDK のアクティベーション コンテキストを似ています。 注意してください。

アクティベーション コンテキストは、次の方法では、MFC アプリケーション、ユーザーの Dll、および MFC 拡張 Dll で機能します。

- MFC アプリケーションでは、自身のマニフェスト リソースのリソース ID 1 を使用します。 この場合、MFC では、独自のアクティベーション コンテキストを作成できませんが、既定のアプリケーション コンテキストを使用します。

- ユーザーの MFC Dll は、自身のマニフェスト リソースのリソース ID が 2 を使用します。 ここでは、MFC は、別のユーザーの Dll は、異なるバージョンの同じライブラリ (コモン コントロール ライブラリなど) を使用できるように、各ユーザー DLL のアクティベーション コンテキストを作成します。

- MFC 拡張 Dll は、ホスティング アプリケーションやユーザーに Dll のアクティベーション コンテキストを確立するために依存しています。

説明されているプロセスを使用してアクティブ化コンテキストの状態を変更できますが[アクティブ化コンテキストの API を使用して](/windows/desktop/SbsCs/using-the-activation-context-api)MFC のアクティベーション コンテキストのメカニズムを使用して役に立ちます DLL ベースのプラグイン アーキテクチャを開発する場合簡単に (または不可能) 外部プラグインに個々 の呼び出しの前後に手動でアクティブ化の状態を切り替える。

アクティブ化コンテキストが作成された[AfxWinInit](../mfc/reference/application-information-and-management.md#afxwininit)します。 破棄は、`AFX_MODULE_STATE`デストラクター。 アクティベーション コンテキスト ハンドルに保持される`AFX_MODULE_STATE`します。 (`AFX_MODULE_STATE`は、「 [AfxGetStaticModuleState](reference/extension-dll-macros.md#afxgetstaticmodulestate)。)

[AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state)マクロがアクティブにし、アクティベーション コンテキストを非アクティブ化します。 `AFX_MANAGE_STATE` MFC コード ユーザー DLL によって選択されている適切なライセンス認証のコンテキストで実行できるように、MFC のスタティック ライブラリと MFC の Dll に対して有効です。

## <a name="see-also"></a>関連項目

[アクティベーション コンテキスト](/windows/desktop/SbsCs/activation-contexts)<br/>
[アプリケーション マニフェスト](/windows/desktop/SbsCs/application-manifests)<br/>
[アセンブリ マニフェスト](/windows/desktop/SbsCs/assembly-manifests)<br/>
[AfxWinInit](../mfc/reference/application-information-and-management.md#afxwininit)<br/>
[AfxGetStaticModuleState](reference/extension-dll-macros.md#afxgetstaticmodulestate)<br/>
[AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state)
