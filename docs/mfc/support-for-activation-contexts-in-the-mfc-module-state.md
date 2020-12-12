---
description: 詳細については、「MFC モジュール状態でのアクティベーションコンテキストのサポート」を参照してください。
title: MFC モジュール状態でのアクティベーション コンテキストのサポート
ms.date: 11/04/2016
helpviewer_keywords:
- activation contexts [MFC]
- activation contexts [MFC], MFC support
ms.assetid: 1e49eea9-3620-46dd-bc5f-d664749567c7
ms.openlocfilehash: e7f7434824956ca2a62d75fbd50eb9dd5e01f34e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216471"
---
# <a name="support-for-activation-contexts-in-the-mfc-module-state"></a>MFC モジュール状態でのアクティベーション コンテキストのサポート

MFC では、ユーザーモジュールによって提供されるマニフェストリソースを使用してアクティベーションコンテキストを作成します。 アクティベーションコンテキストの作成方法の詳細については、次のトピックを参照してください。

- [アクティベーションコンテキスト](/windows/win32/SbsCs/activation-contexts)

- [アプリケーションマニフェスト](/windows/win32/SbsCs/application-manifests)

- [アセンブリマニフェスト](/windows/win32/SbsCs/assembly-manifests)

## <a name="remarks"></a>解説

これらの Windows SDK のトピックを読むときは、mfc が Windows SDK Activation context API を使用しない点を除いて、MFC アクティベーションコンテキストメカニズムが Windows SDK アクティベーションコンテキストに似ていることに注意してください。

アクティベーションコンテキストは、次の方法で MFC アプリケーション、ユーザー Dll、および MFC 拡張 Dll で動作します。

- MFC アプリケーションは、マニフェストリソースに対してリソース ID 1 を使用します。 この場合、MFC は独自のアクティベーションコンテキストを作成しませんが、既定のアプリケーションコンテキストを使用します。

- MFC ユーザー Dll は、マニフェストリソースに対してリソース ID 2 を使用します。 ここでは、MFC はユーザー DLL ごとにアクティベーションコンテキストを作成するため、異なるユーザー Dll で同じライブラリの異なるバージョンを使用できます (たとえば、コモンコントロールライブラリ)。

- MFC 拡張 Dll は、ホストしているアプリケーションまたはユーザー Dll を使用してアクティベーションコンテキストを確立します。

アクティベーションコンテキストの状態は、「 [アクティベーションコンテキスト API の使用](/windows/win32/SbsCs/using-the-activation-context-api)」で説明されているプロセスを使用して変更できますが、MFC アクティベーションコンテキスト機構を使用すると、外部プラグインを個別に呼び出す前後に手動でアクティベーション状態を切り替えることができない DLL ベースのプラグインアーキテクチャを開発する場合に便利です。

アクティベーションコンテキストは、 [AfxWinInit](../mfc/reference/application-information-and-management.md#afxwininit)で作成されます。 デストラクターでは破棄され `AFX_MODULE_STATE` ます。 アクティベーションコンテキストハンドルは、に保持され `AFX_MODULE_STATE` ます。 ( `AFX_MODULE_STATE` は [AfxGetStaticModuleState](reference/extension-dll-macros.md#afxgetstaticmodulestate)に記述されています)。

[AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state)マクロはアクティブ化コンテキストをアクティブ化し、非アクティブにします。 `AFX_MANAGE_STATE` を使用すると、mfc Dll に加えて、静的な MFC ライブラリに対して、ユーザー DLL によって選択された適切なアクティベーションコンテキストで MFC コードを実行できるようになります。

## <a name="see-also"></a>関連項目

[アクティベーションコンテキスト](/windows/win32/SbsCs/activation-contexts)<br/>
[アプリケーションマニフェスト](/windows/win32/SbsCs/application-manifests)<br/>
[アセンブリマニフェスト](/windows/win32/SbsCs/assembly-manifests)<br/>
[AfxWinInit](../mfc/reference/application-information-and-management.md#afxwininit)<br/>
[AfxGetStaticModuleState](reference/extension-dll-macros.md#afxgetstaticmodulestate)<br/>
[AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state)
