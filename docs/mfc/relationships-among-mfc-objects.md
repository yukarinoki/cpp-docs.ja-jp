---
title: 各種 MFC オブジェクト間のリレーションシップ |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, relationships between key objects
- objects [MFC], relationships
- relationships, MFC objects
- MFC object relationships
ms.assetid: 6e8f3b51-e80f-4d88-94c8-4c1e4ee163ad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d2f42f754157a4fc2e3f3e1aa40f38477b982e16
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46372484"
---
# <a name="relationships-among-mfc-objects"></a>各種 MFC オブジェクト間の関係

パースペクティブに、ドキュメント/ビューの作成プロセスを配置するには、実行中のプログラムを検討してください: ドキュメント、ビューを含めるために使用するフレーム ウィンドウおよびドキュメントに関連付けられたビュー。

- ドキュメントでは、ドキュメントを作成するドキュメント テンプレートへのポインター、そのドキュメントのビューの一覧を保持します。

- ビューは、そのドキュメントへのポインターを保持し、親フレーム ウィンドウの子です。

- ドキュメント フレーム ウィンドウは、その現在のアクティブなビューへのポインターを保持します。

- ドキュメント テンプレートは、開いているドキュメントの一覧を保持します。

- アプリケーションでは、そのドキュメント テンプレートの一覧を保持します。

- Windows は追跡のすべてのウィンドウにメッセージを送信できるようにします。

ドキュメント/ビューの作成時に、これらの関係が確立されています。 次の表では、実行中のプログラム内のオブジェクトが他のオブジェクトにアクセスする方法を示します。 任意のオブジェクトは、グローバル関数を呼び出すことによって、アプリケーション オブジェクトへのポインターを取得できます[AfxGetApp](../mfc/reference/application-information-and-management.md#afxgetapp)します。

### <a name="gaining-access-to-other-objects-in-your-application"></a>アプリケーションの他のオブジェクトへのアクセス

|オブジェクトから|その他のオブジェクトにアクセスする方法|
|-----------------|---------------------------------|
|ドキュメント|使用[GetFirstViewPosition](../mfc/reference/cdocument-class.md#getfirstviewposition)と[GetNextView](../mfc/reference/cdocument-class.md#getnextview)ドキュメントのビューの一覧にアクセスします。<br /><br /> 呼び出す[GetDocTemplate](../mfc/reference/cdocument-class.md#getdoctemplate)ドキュメント テンプレートを取得します。|
|表示|呼び出す[GetDocument](../mfc/reference/cview-class.md#getdocument)ドキュメントを取得します。<br /><br /> 呼び出す[GetParentFrame](../mfc/reference/cwnd-class.md#getparentframe)フレーム ウィンドウを取得します。|
|ドキュメント フレーム ウィンドウ|呼び出す[GetActiveView](../mfc/reference/cframewnd-class.md#getactiveview)を現在のビューを取得します。<br /><br /> 呼び出す[GetActiveDocument](../mfc/reference/cframewnd-class.md#getactivedocument)を現在のビューにアタッチされているドキュメントを取得します。|
|MDI フレーム ウィンドウ|呼び出す[MDIGetActive](../mfc/reference/cmdiframewnd-class.md#mdigetactive)を現在アクティブな取得[CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)します。|

通常、フレーム ウィンドウが 1 つのビューが、場合によっては、分割ウィンドウでは、ように同じフレーム ウィンドウに、複数のビュー。 フレーム ウィンドウが現在アクティブなビューにポインターを保持します。ポインターは、別のビューがアクティブになる任意の時点で更新されます。

> [!NOTE]
>  メイン フレーム ウィンドウへのポインターが格納されている、 [m_pMainWnd](../mfc/reference/cwinthread-class.md#m_pmainwnd)アプリケーション オブジェクトのメンバー変数。 呼び出し`OnFileNew`のオーバーライドで、`InitInstance`のメンバー関数`CWinApp`設定*m_pMainWnd*できます。 呼び出さない場合`OnFileNew`で変数の値を設定する必要があります`InitInstance`自分でします。 (SDI COM コンポーネント (サーバー) のアプリケーションは設定できません変数場合は、コマンドラインで/Embedding。)なお*m_pMainWnd*クラスのメンバーであるようになりました`CWinThread`なく`CWinApp`します。

## <a name="see-also"></a>関連項目

[ドキュメント テンプレートとドキュメント/ビューの作成手順](../mfc/document-templates-and-the-document-view-creation-process.md)<br/>
[ドキュメント テンプレートの作成](../mfc/document-template-creation.md)<br/>
[ドキュメント/ビューの作成](../mfc/document-view-creation.md)<br/>
[新しいドキュメント、ウィンドウ、ビューの作成](../mfc/creating-new-documents-windows-and-views.md)

