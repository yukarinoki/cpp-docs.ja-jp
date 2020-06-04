---
title: OLE コントロール クラス
ms.date: 11/04/2016
helpviewer_keywords:
- ActiveX classes [MFC]
- custom controls [MFC], classes
- ActiveX controls [MFC], OLE control classes
- ActiveX control classes [MFC]
- OLE controls [MFC], classes
- OLE control classes [MFC]
- reusable component classes [MFC]
ms.assetid: 96495ec3-319e-4163-b839-1af0428ed9dd
ms.openlocfilehash: 47c28520d592c4bd49ab6cb40edbb2f5ddf59846
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447645"
---
# <a name="ole-control-classes"></a>OLE コントロール クラス

これらは、OLE コントロールを記述するときに使用する主要なクラスです。 OLE コントロールモジュールの `COleControlModule` クラスは、アプリケーションの[CWinApp](../mfc/reference/cwinapp-class.md)クラスに似ています。 各モジュールは、1つまたは複数の OLE コントロールを実装します。これらのコントロールは `COleControl` のオブジェクトによって表されます。 これらのコントロールは `CConnectionPoint` オブジェクトを使用してコンテナーと通信します。

`CPictureHolder` クラスと `CFontHolder` クラスは、画像とフォントの COM インターフェイスをカプセル化します。一方、`COlePropertyPage` および `CPropExchange` クラスは、プロパティページとコントロールのプロパティの永続化を実装するのに役立ちます。

[COleControlModule](../mfc/reference/colecontrolmodule-class.md)<br/>
OLE コントロールモジュールの `CWinApp` クラスを置き換えます。 `COleControlModule` クラスから派生させて、OLE コントロールモジュールオブジェクトを開発します。 OLE コントロールのモジュールを初期化するためのメンバー関数が用意されています。

[COleControl](../mfc/reference/colecontrol-class.md)<br/>
`COleControl` クラスから派生させて、OLE コントロールを開発します。 `CWnd`から派生したこのクラスは、Windows ウィンドウオブジェクトのすべての機能に加えて、イベントの発生やメソッドとプロパティをサポートする機能などの追加の OLE 固有の機能を継承します。

[CConnectionPoint](../mfc/reference/cconnectionpoint-class.md)<br/>
`CConnectionPoint` クラスは、コネクションポイントと呼ばれる他の OLE オブジェクトとの通信に使用される特別な種類のインターフェイスを定義します。 コネクションポイントは、イベントの発生や通知の変更など、他のオブジェクトに対するアクションを開始できる送信インターフェイスを実装します。

[CPictureHolder](../mfc/reference/cpictureholder-class.md)<br/>
Windows picture オブジェクトと `IPicture` COM インターフェイスの機能をカプセル化します。OLE コントロールのカスタム Picture プロパティを実装するために使用されます。

[CFontHolder](../mfc/reference/cfontholder-class.md)<br/>
Windows のフォントオブジェクトと `IFont` COM インターフェイスの機能をカプセル化します。OLE コントロールのストックフォントプロパティを実装するために使用されます。

[COlePropertyPage](../mfc/reference/colepropertypage-class.md)<br/>
ダイアログボックスと同様に、グラフィカルインターフェイスに OLE コントロールのプロパティを表示します。

[CPropExchange](../mfc/reference/cpropexchange-class.md)<br/>
OLE コントロールのプロパティ永続化の実装をサポートします。 ダイアログボックスの[CDataExchange](../mfc/reference/cdataexchange-class.md)に似ています。

[CMonikerFile](../mfc/reference/cmonikerfile-class.md)<br/>
モニカーを取得します。また、モニカーにすることができる文字列形式を受け取り、モニカーが名前であるストリームに同期的にバインドします。

[CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md)<br/>
`CMonikerFile`と同様に機能します。ただし、モニカーは、モニカーが名前であるストリームに非同期的にバインドされます。

[CDataPathProperty](../mfc/reference/cdatapathproperty-class.md)<br/>
非同期で読み込める OLE コントロール プロパティを実装します。

[CCachedDataPathProperty](../mfc/reference/ccacheddatapathproperty-class.md)<br/>
非同期で転送し、メモリ ファイルにキャッシュする OLE コントロール プロパティを実装します。

[COleCmdUI](../mfc/reference/colecmdui-class.md)<br/>
アクティブなドキュメントが、コンテナーのユーザーインターフェイス (FileNew、Open、Print など) で発生したコマンドを受け取ることができるようにします。また、コンテナーは、アクティブなドキュメントのユーザーインターフェイスで生成されたコマンドを受け取ることができます。

[COleSafeArray](../mfc/reference/colesafearray-class.md)<br/>
任意の型および次元の配列を操作します。

## <a name="see-also"></a>参照

[クラスの概要](../mfc/class-library-overview.md)
