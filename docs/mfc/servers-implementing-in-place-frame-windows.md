---
title: 'サーバー : 埋め込み先フレーム ウィンドウの実装'
ms.date: 09/09/2019
helpviewer_keywords:
- frame windows [MFC], implementing
- OLE server applications [MFC], frame windows
- servers, in-place frame windows
- frame windows [MFC], in-place
- in-place frame windows
ms.assetid: 09bde4d8-15e2-4fba-8d14-9b954d926b92
ms.openlocfilehash: a082afe141a21e4175886f13a26043694ac0d426
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230468"
---
# <a name="servers-implementing-in-place-frame-windows"></a>サーバー : 埋め込み先フレーム ウィンドウの実装

この記事では、アプリケーションウィザードを使用してサーバーアプリケーションを作成しない場合に、ビジュアル編集サーバーアプリケーションに埋め込み先フレームウィンドウを実装するために必要な作業について説明します。 この記事で説明されている手順に従って、アプリケーションウィザードで生成されたアプリケーションまたは Visual C++ で提供されているサンプルの既存のインプレースフレームウィンドウクラスを使用できます。

#### <a name="to-declare-an-in-place-frame-window-class"></a>埋め込み先フレームウィンドウクラスを宣言するには

1. の埋め込み先フレームウィンドウクラスを派生させ `COleIPFrameWnd` ます。

   - クラスヘッダーファイルで DECLARE_DYNCREATE マクロを使用します。

   - クラス実装 (.cpp) ファイルで IMPLEMENT_DYNCREATE マクロを使用します。 これにより、このクラスのオブジェクトがフレームワークによって作成されます。

1. `COleResizeBar`フレームウィンドウクラスでメンバーを宣言します。 これは、サーバーアプリケーションでのインプレースサイズ変更をサポートする場合に必要です。

   `OnCreate`([クラスウィザード](reference/mfc-class-wizard.md)を使用して) メッセージハンドラーを宣言し、 `Create` `COleResizeBar` メンバーを定義している場合はを呼び出します。

1. ツールバーがある場合は、 `CToolBar` フレームウィンドウクラスでメンバーを宣言します。

   `OnCreateControlBars`サーバーが適切に配置されている場合は、メンバー関数をオーバーライドしてツールバーを作成します。 次に例を示します。

   [!code-cpp[NVC_MFCOleServer#1](../mfc/codesnippet/cpp/servers-implementing-in-place-frame-windows_1.cpp)]

   手順5の次のコードについて説明します。

1. メインの .cpp ファイルに、このインプレースフレームウィンドウクラスのヘッダーファイルを含めます。

1. `InitInstance`アプリケーションクラスの場合は、 `SetServerInfo` ドキュメントテンプレートオブジェクトの関数を呼び出して、オープンおよびインプレース編集で使用するリソースと埋め込み先フレームウィンドウを指定します。

ステートメント内の一連の関数呼び出しによって、 **`if`** サーバーが提供するリソースからツールバーが作成されます。 この時点で、ツールバーはコンテナーのウィンドウ階層の一部です。 このツールバーはから派生しているので、 `CToolBar` 所有者を変更しない限り、メッセージはコンテナーアプリケーションのフレームウィンドウである所有者に渡されます。 そのため、を呼び出す `SetOwner` 必要があります。 この呼び出しによって、コマンドがサーバーの埋め込み先フレームウィンドウとして送信されるウィンドウが変更され、メッセージがサーバーに渡されます。 これにより、サーバーは、提供されているツールバーに対する操作に対応できます。

ツールバーのビットマップの ID は、サーバーアプリケーションで定義されている他のインプレースリソースと同じである必要があります。 詳細については[、「メニューとリソース: サーバーの追加](../mfc/menus-and-resources-server-additions.md)」を参照してください。

詳細については、*クラスライブラリリファレンス*の「 [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md)、 [Coleresizebar](../mfc/reference/coleresizebar-class.md)、および[CDocTemplate:: setserverinfo](../mfc/reference/cdoctemplate-class.md#setserverinfo) 」を参照してください。

## <a name="see-also"></a>関連項目

[サーバー](../mfc/servers.md)<br/>
[サーバー: サーバーの実装](../mfc/servers-implementing-a-server.md)<br/>
[サーバー: サーバードキュメントの実装](../mfc/servers-implementing-server-documents.md)<br/>
[サーバー: サーバー項目](../mfc/servers-server-items.md)
