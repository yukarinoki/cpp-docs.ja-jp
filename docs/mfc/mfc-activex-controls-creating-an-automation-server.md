---
title: 'MFC ActiveX コントロール : オートメーション サーバーの作成'
ms.date: 11/04/2016
helpviewer_keywords:
- Automation servers [MFC], MFC ActiveX controls
- ActiveX controls [MFC], Automation server
- MFC ActiveX controls [MFC], Automation server
ms.assetid: e0c24ed2-d61c-49ad-a4fa-4e1098d1d39b
ms.openlocfilehash: f2c941e43e810845560b4c35c558ec70248c21ed
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84622381"
---
# <a name="mfc-activex-controls-creating-an-automation-server"></a>MFC ActiveX コントロール : オートメーション サーバーの作成

プログラムを使用してそのコントロールを別のアプリケーションに埋め込み、アプリケーションからコントロール内のメソッドを呼び出すために、オートメーションサーバーとして MFC ActiveX コントロールを開発できます。 このようなコントロールは、ActiveX コントロールコンテナーで引き続きホストできます。

### <a name="to-create-a-control-as-an-automation-server"></a>オートメーションサーバーとしてコントロールを作成するには

1. コントロールを[作成](reference/mfc-activex-control-wizard.md)します。

1. [メソッドを追加](mfc-activex-controls-methods.md)します。

1. [Isinvokeallowed](reference/colecontrol-class.md#isinvokeallowed)をオーバーライドします。

1. コントロールをビルドします。

### <a name="to-programmatically-access-the-methods-in-an-automation-server"></a>オートメーションサーバーでプログラムによってメソッドにアクセスするには

1. [MFC exe](reference/mfc-application-wizard.md)などのアプリケーションを作成します。

1. 関数の先頭に、 `InitInstance` 次の行を追加します。

   [!code-cpp[NVC_MFC_AxCont#17](codesnippet/cpp/mfc-activex-controls-creating-an-automation-server_1.cpp)]

1. クラスビューで、プロジェクトノードを右クリックし、[ **typelib からクラスを追加**] を選択してタイプライブラリをインポートします。

   これにより、ファイル名拡張子 .h と .cpp のファイルがプロジェクトに追加されます。

1. ActiveX コントロールで1つ以上のメソッドを呼び出すクラスのヘッダーファイルで、次の行を追加します。 `#include filename.h` ここで、file name はタイプライブラリをインポートしたときに作成されたヘッダーファイルの名前です。

1. ActiveX コントロールのメソッドへの呼び出しが行われる関数では、コントロールのラッパークラスのオブジェクトを作成し、ActiveX オブジェクトを作成するコードを追加します。 たとえば、次の MFC コードでは、コントロールをインスタンス化し、 `CCirc` Caption プロパティを取得して、ダイアログボックスで [OK] ボタンをクリックしたときに結果を表示します。

   [!code-cpp[NVC_MFC_AxCont#18](codesnippet/cpp/mfc-activex-controls-creating-an-automation-server_2.cpp)]

ActiveX コントロールをアプリケーションで使用した後に、そのコントロールにメソッドを追加する場合は、タイプライブラリをインポートしたときに作成されたファイルを削除することによって、アプリケーションで最新バージョンのコントロールの使用を開始できます。 その後、タイプライブラリをもう一度インポートします。

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール](mfc-activex-controls.md)
