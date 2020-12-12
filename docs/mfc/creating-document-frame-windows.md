---
description: 詳細については、ドキュメントフレームウィンドウの作成に関するページを参照してください。
title: ドキュメント フレーム ウィンドウの作成
ms.date: 11/04/2016
helpviewer_keywords:
- frame windows [MFC], creating
- document templates [MFC], and document frame windows
- windows [MFC], creating
- runtime, class information
- run-time class [MFC], and document frame window creation
- document frame windows [MFC], creating
- MFC, frame windows
ms.assetid: 8671e239-b76f-4dea-afa8-7024e6e58ff5
ms.openlocfilehash: e2c4f72ab56045df7bb121be3bb557314780fedb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97309811"
---
# <a name="creating-document-frame-windows"></a>ドキュメント フレーム ウィンドウの作成

[ドキュメント/ビューの作成](document-view-creation.md) では、 [CDocTemplate](reference/cdoctemplate-class.md) オブジェクトがフレームウィンドウ、ドキュメント、およびビューの作成を調整し、それらをまとめて接続する方法を示します。 コンストラクターに対する3つの [CRuntimeClass](reference/cruntimeclass-structure.md) 引数は、[ `CDocTemplate` ファイル] メニューまたは [MDI ウィンドウ] メニューの [新規作成] コマンドなどのユーザーコマンドに応答して、ドキュメントテンプレートによって動的に作成されるフレームウィンドウ、ドキュメント、およびビュークラスを指定します。 ドキュメントテンプレートは、ビューとドキュメントのフレームウィンドウを作成するときに、後で使用するためにこの情報を保存します。

[RUNTIME_CLASS](reference/run-time-object-model-services.md#runtime_class)メカニズムが正常に機能するには、派生フレームウィンドウクラスを[DECLARE_DYNCREATE](reference/run-time-object-model-services.md#declare_dyncreate)マクロで宣言する必要があります。 これは、フレームワークがクラスの動的構築機構を使用してドキュメントフレームウィンドウを作成する必要があるためです `CObject` 。

ユーザーがドキュメントを作成するコマンドを選択すると、フレームワークはドキュメントテンプレートに対してを呼び出し、ドキュメントオブジェクト、ビュー、およびビューを表示するフレームウィンドウを作成します。 ドキュメントフレームウィンドウを作成すると、ドキュメントテンプレートによって、適切なクラスのオブジェクトが作成されます。これは、SDI アプリケーションの場合は [CFrameWnd](reference/cframewnd-class.md) から派生したクラス、または MDI アプリケーションの場合は [CMDIChildWnd](reference/cmdichildwnd-class.md) から派生したクラスです。 次に、フレームワークは、フレームウィンドウオブジェクトの [LoadFrame](reference/cframewnd-class.md#loadframe) メンバー関数を呼び出して、リソースから作成情報を取得し、Windows ウィンドウを作成します。 フレームワークは、ウィンドウハンドルをフレームウィンドウオブジェクトにアタッチします。 次に、ドキュメントフレームウィンドウの子ウィンドウとしてビューを作成します。

派生したオブジェクト [を初期化するタイミング](when-to-initialize-cwnd-objects.md) を決定するときは、注意して `CWnd` ください。

## <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [CObject からクラスを派生する (その動的作成機構)](deriving-a-class-from-cobject.md)

- [ドキュメント/ビューの作成 (テンプレートとフレームウィンドウの作成)](document-view-creation.md)

- [フレーム ウィンドウの破棄](destroying-frame-windows.md)

## <a name="see-also"></a>関連項目

[フレームウィンドウの使用](using-frame-windows.md)
