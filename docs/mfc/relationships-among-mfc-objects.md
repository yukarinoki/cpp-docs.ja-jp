---
description: '詳細情報: MFC オブジェクト間の関係'
title: 各種 MFC オブジェクト間の関係
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, relationships between key objects
- objects [MFC], relationships
- relationships, MFC objects
- MFC object relationships
ms.assetid: 6e8f3b51-e80f-4d88-94c8-4c1e4ee163ad
ms.openlocfilehash: 0646d487d1d60293461316edddcb97fde30905a8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218057"
---
# <a name="relationships-among-mfc-objects"></a>各種 MFC オブジェクト間の関係

ドキュメント/ビューの作成プロセスをパースペクティブに配置するには、実行中のプログラム (ドキュメント、ビューを格納するために使用されるフレームウィンドウ、およびドキュメントに関連付けられたビュー) を検討してください。

- ドキュメントには、そのドキュメントのビューの一覧と、ドキュメントを作成したドキュメントテンプレートへのポインターが保持されます。

- ビューはそのドキュメントへのポインターを保持し、親フレームウィンドウの子になります。

- ドキュメントフレームウィンドウには、現在のアクティブなビューへのポインターが保持されます。

- ドキュメントテンプレートは、開いているドキュメントの一覧を保持します。

- アプリケーションは、ドキュメントテンプレートの一覧を保持します。

- Windows は、開いているすべてのウィンドウを追跡して、メッセージを送信できるようにします。

これらの関係は、ドキュメント/ビューの作成時に確立されます。 次の表は、実行中のプログラムのオブジェクトが他のオブジェクトにアクセスする方法を示しています。 すべてのオブジェクトは、グローバル関数 [AfxGetApp](../mfc/reference/application-information-and-management.md#afxgetapp)を呼び出すことによって、アプリケーションオブジェクトへのポインターを取得できます。

### <a name="gaining-access-to-other-objects-in-your-application"></a>アプリケーション内の他のオブジェクトへのアクセスを取得する

|From オブジェクト|他のオブジェクトにアクセスする方法|
|-----------------|---------------------------------|
|ドキュメント|ドキュメントのビューリストにアクセスするには、 [Getfirstviewposition](../mfc/reference/cdocument-class.md#getfirstviewposition) と [GetNextView](../mfc/reference/cdocument-class.md#getnextview) を使用します。<br /><br /> ドキュメントテンプレートを取得するには、 [GetDocTemplate](../mfc/reference/cdocument-class.md#getdoctemplate) を呼び出します。|
|表示|ドキュメントを取得するには、 [Getdocument](../mfc/reference/cview-class.md#getdocument) を呼び出します。<br /><br /> [GetParentFrame](../mfc/reference/cwnd-class.md#getparentframe)を呼び出して、フレームウィンドウを取得します。|
|ドキュメントフレームウィンドウ|[Getactiveview](../mfc/reference/cframewnd-class.md#getactiveview)を呼び出して、現在のビューを取得します。<br /><br /> [GetActiveDocument](../mfc/reference/cframewnd-class.md#getactivedocument)を呼び出して、現在のビューにアタッチされているドキュメントを取得します。|
|MDI フレームウィンドウ|[Mdigetactive](../mfc/reference/cmdiframewnd-class.md#mdigetactive)を呼び出して、現在アクティブな[CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)を取得します。|

通常、フレームウィンドウには1つのビューがありますが、分割ウィンドウと同様に、同じフレームウィンドウに複数のビューが含まれている場合もあります。 フレームウィンドウには、現在アクティブなビューへのポインターが保持されます。ポインターは、別のビューがアクティブ化されるたびに更新されます。

> [!NOTE]
> メインフレームウィンドウへのポインターは、アプリケーションオブジェクトの [m_pMainWnd](../mfc/reference/cwinthread-class.md#m_pmainwnd) メンバー変数に格納されます。 `OnFileNew`のメンバー関数のオーバーライドでを呼び出すと、 `InitInstance` `CWinApp` *m_pMainWnd* が設定されます。 を呼び出さない場合は `OnFileNew` 、変数の値を自分で設定する必要があり `InitInstance` ます。 (コマンドラインで/Embedding が実行されている場合、SDI COM コンポーネント (サーバー) アプリケーションで変数を設定することはできません)。 *M_pMainWnd* は、ではなくクラスのメンバーになっていることに注意 `CWinThread` して `CWinApp` ください。

## <a name="see-also"></a>関連項目

[ドキュメントテンプレートとドキュメント/ビュー作成プロセス](../mfc/document-templates-and-the-document-view-creation-process.md)<br/>
[ドキュメントテンプレートの作成](../mfc/document-template-creation.md)<br/>
[ドキュメント/ビューの作成](../mfc/document-view-creation.md)<br/>
[新しいドキュメント、ウィンドウ、およびビューの作成](../mfc/creating-new-documents-windows-and-views.md)
