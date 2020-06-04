---
title: 各種 MFC オブジェクト間の関係
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, relationships between key objects
- objects [MFC], relationships
- relationships, MFC objects
- MFC object relationships
ms.assetid: 6e8f3b51-e80f-4d88-94c8-4c1e4ee163ad
ms.openlocfilehash: d7e40e25b405d3f8ec50a518889cc2b89bc8c725
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372808"
---
# <a name="relationships-among-mfc-objects"></a>各種 MFC オブジェクト間の関係

ドキュメント/ビュー作成プロセスをパースペクティブに配置するには、実行中のプログラム(ドキュメント、ビューを含めるために使用されるフレーム ウィンドウ、およびドキュメントに関連付けられたビュー)を検討してください。

- ドキュメントには、そのドキュメントのビューの一覧と、ドキュメントを作成したドキュメント テンプレートへのポインタが保持されます。

- ビューは、ドキュメントへのポインターを保持し、親フレーム ウィンドウの子です。

- ドキュメント フレーム ウィンドウは、現在アクティブなビューへのポインターを保持します。

- 文書テンプレートは、開いている文書のリストを保持します。

- アプリケーションは、ドキュメント テンプレートのリストを保持します。

- Windows は、開いているすべてのウィンドウを追跡し、メッセージを送信できるようにします。

これらの関係は、ドキュメント/ビューの作成時に確立されます。 次の表は、実行中のプログラム内のオブジェクトが他のオブジェクトにアクセスする方法を示しています。 グローバル関数[AfxGetApp](../mfc/reference/application-information-and-management.md#afxgetapp)を呼び出すことによって、任意のオブジェクトがアプリケーション オブジェクトへのポインターを取得できます。

### <a name="gaining-access-to-other-objects-in-your-application"></a>アプリケーション内の他のオブジェクトへのアクセス権を取得する

|オブジェクトから|他のオブジェクトにアクセスする方法|
|-----------------|---------------------------------|
|ドキュメント|ドキュメントのビュー リストにアクセスするには[、GetFirstViewPosition](../mfc/reference/cdocument-class.md#getfirstviewposition)および[GetNextView](../mfc/reference/cdocument-class.md#getnextview)を使用します。<br /><br /> を[呼び](../mfc/reference/cdocument-class.md#getdoctemplate)出して、ドキュメント テンプレートを取得します。|
|表示|[GetDocument を](../mfc/reference/cview-class.md#getdocument)呼び出してドキュメントを取得します。<br /><br /> フレーム ウィンドウを[取得するには、GetParentFrame](../mfc/reference/cwnd-class.md#getparentframe)を呼び出します。|
|ドキュメント フレーム ウィンドウ|現在[のビューを取得するには、GetActiveView](../mfc/reference/cframewnd-class.md#getactiveview)を呼び出します。<br /><br /> 現在のビューに添付されたドキュメントを取得するには[、GetActiveDocument](../mfc/reference/cframewnd-class.md#getactivedocument)を呼び出します。|
|MDI フレーム ウィンドウ|現在アクティブな[CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)を取得するには[、MDIGetActive](../mfc/reference/cmdiframewnd-class.md#mdigetactive)を呼び出します。|

通常、フレーム ウィンドウには 1 つのビューがありますが、分割ウィンドウのように、同じフレーム ウィンドウに複数のビューが含まれる場合があります。 フレーム ウィンドウは、現在アクティブなビューへのポインターを保持します。ポインタは、別のビューがアクティブになると更新されます。

> [!NOTE]
> メイン フレーム ウィンドウへのポインターは、アプリケーション オブジェクトの[m_pMainWnd](../mfc/reference/cwinthread-class.md#m_pmainwnd)メンバー変数に格納されます。 セットの`InitInstance`メンバー`OnFileNew`関数のオーバーライドでの呼び出し*m_pMainWnd。* `CWinApp` を呼び出`OnFileNew`さない場合は、変数の値を自分自身で`InitInstance`設定する必要があります。 (/Embedding がコマンド ライン上にある場合、SDI COM コンポーネント (サーバー) アプリケーションは変数を設定できません。*m_pMainWnd*は、 ではなく`CWinThread``CWinApp`クラスのメンバーになっていることに注意してください。

## <a name="see-also"></a>関連項目

[ドキュメント テンプレートとドキュメント/ビュー作成プロセス](../mfc/document-templates-and-the-document-view-creation-process.md)<br/>
[ドキュメント テンプレートの作成](../mfc/document-template-creation.md)<br/>
[ドキュメントおよびビューの作成](../mfc/document-view-creation.md)<br/>
[新しいドキュメント、ウィンドウ、およびビューの作成](../mfc/creating-new-documents-windows-and-views.md)
