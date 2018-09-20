---
title: 'MFC ActiveX コントロール: オートメーション サーバーの作成 |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Automation servers [MFC], MFC ActiveX controls
- ActiveX controls [MFC], Automation server
- MFC ActiveX controls [MFC], Automation server
ms.assetid: e0c24ed2-d61c-49ad-a4fa-4e1098d1d39b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5fa8370bb02e71c457f7967d5cb6b508e743333e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46373936"
---
# <a name="mfc-activex-controls-creating-an-automation-server"></a>MFC ActiveX コントロール : オートメーション サーバーの作成

MFC ActiveX コントロールは、別のアプリケーションでそのコントロールを埋め込むと、アプリケーションのコントロールのメソッドを呼び出すことをプログラムでの目的でオートメーション サーバーとして開発できます。 このようなコントロールは ActiveX コントロール コンテナーでホストできますもよい。

### <a name="to-create-a-control-as-an-automation-server"></a>オートメーション サーバーとしてコントロールを作成するには

1. [作成](../mfc/reference/mfc-activex-control-wizard.md)コントロール。

1. [メソッドを追加](../mfc/mfc-activex-controls-methods.md)します。

1. オーバーライド[オーバーライド](../mfc/reference/colecontrol-class.md#isinvokeallowed)します。 詳細については、サポート技術情報記事 Q146120 を参照してください。

1. コントロールをビルドします。

### <a name="to-programmatically-access-the-methods-in-an-automation-server"></a>オートメーション サーバーでメソッドをプログラムでアクセスするには

1. たとえば、アプリケーションを作成、 [MFC exe](../mfc/reference/mfc-application-wizard.md)します。

1. 先頭に、`InitInstance`関数は、次の行を追加します。

     [!code-cpp[NVC_MFC_AxCont#17](../mfc/codesnippet/cpp/mfc-activex-controls-creating-an-automation-server_1.cpp)]

1. クラス ビューでは、プロジェクト ノードを右クリックして**typelib クラス追加**タイプ ライブラリをインポートします。

     これにより、ファイル名拡張子の .h および .cpp ファイルがプロジェクトに追加されます。

1. ヘッダー ファイルでクラスの ActiveX コントロールの 1 つまたは複数のメソッドを呼び出すことは、次の行を追加します:`#include filename.h`ファイル名は、タイプ ライブラリをインポートしたときに作成されたヘッダー ファイルの名前です。

1. ActiveX コントロールのメソッドの呼び出しを行ったは関数では、コントロールのラッパー クラスのオブジェクトを作成するコードを追加し、ActiveX オブジェクトを作成します。 たとえば、次の MFC コードがインスタンス化、`CCirc`制御、キャプションのプロパティを取得およびダイアログ ボックスで [ok] ボタンがクリックされたときに、結果を表示します。

     [!code-cpp[NVC_MFC_AxCont#18](../mfc/codesnippet/cpp/mfc-activex-controls-creating-an-automation-server_2.cpp)]

アプリケーションで使用した後、ActiveX コントロールにメソッドを追加する場合は、タイプ ライブラリをインポートしたときに作成されたファイルを削除するアプリケーションでコントロールの最新バージョンの使用を開始できます。 再度、タイプ ライブラリをインポートします。

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)

