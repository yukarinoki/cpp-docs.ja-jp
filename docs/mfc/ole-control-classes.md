---
description: '詳細情報: OLE コントロールクラス'
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
ms.openlocfilehash: da59fcd66fa21602ad864deecac9f568bd5123bc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97244148"
---
# <a name="ole-control-classes"></a>OLE コントロール クラス

これらは、OLE コントロールを記述するときに使用する主要なクラスです。 `COleControlModule`OLE コントロールモジュールのクラスは、アプリケーションの[CWinApp](reference/cwinapp-class.md)クラスに似ています。 各モジュールは、1つまたは複数の OLE コントロールを実装します。これらのコントロールは、オブジェクトによって表され `COleControl` ます。 これらのコントロールは、オブジェクトを使用してコンテナーと通信し `CConnectionPoint` ます。

クラスとクラスは、 `CPictureHolder` `CFontHolder` 画像とフォントの COM インターフェイスをカプセル化し `COlePropertyPage` `CPropExchange` ます。クラスとクラスは、プロパティページとコントロールのプロパティの永続化を実装するのに役立ちます。

[COleControlModule](reference/colecontrolmodule-class.md)<br/>
`CWinApp`OLE コントロールモジュールのクラスを置き換えます。 クラスから派生させて、 `COleControlModule` OLE コントロールモジュールオブジェクトを開発します。 OLE コントロールのモジュールを初期化するためのメンバー関数が用意されています。

[COleControl](reference/colecontrol-class.md)<br/>
`COleControl`OLE コントロールを開発するには、クラスから派生させます。 から派生した `CWnd` このクラスは、Windows ウィンドウオブジェクトのすべての機能に加えて、イベントの発生やメソッドとプロパティをサポートする機能などの追加の OLE 固有の機能を継承します。

[CConnectionPoint](reference/cconnectionpoint-class.md)<br/>
クラスは、 `CConnectionPoint` コネクションポイントと呼ばれる他の OLE オブジェクトとの通信に使用される特別な種類のインターフェイスを定義します。 コネクションポイントは、イベントの発生や通知の変更など、他のオブジェクトに対するアクションを開始できる送信インターフェイスを実装します。

[CPictureHolder](reference/cpictureholder-class.md)<br/>
Windows picture オブジェクトと COM インターフェイスの機能をカプセル化します `IPicture` 。 OLE コントロールのカスタム picture プロパティを実装するために使用されます。

[CFontHolder](reference/cfontholder-class.md)<br/>
Windows フォントオブジェクトおよび COM インターフェイスの機能をカプセル化します `IFont` 。 OLE コントロールのストックフォントプロパティを実装するために使用されます。

[COlePropertyPage](reference/colepropertypage-class.md)<br/>
ダイアログボックスと同様に、グラフィカルインターフェイスに OLE コントロールのプロパティを表示します。

[CPropExchange](reference/cpropexchange-class.md)<br/>
OLE コントロールのプロパティ永続化の実装をサポートします。 ダイアログボックスの [CDataExchange](reference/cdataexchange-class.md) に似ています。

[CMonikerFile](reference/cmonikerfile-class.md)<br/>
モニカーを取得します。また、モニカーにすることができる文字列形式を受け取り、モニカーが名前であるストリームに同期的にバインドします。

[CAsyncMonikerFile](reference/casyncmonikerfile-class.md)<br/>
と同様に機能しますが、モニカー `CMonikerFile` が名前であるストリームにモニカーを非同期的にバインドします。

[CDataPathProperty](reference/cdatapathproperty-class.md)<br/>
非同期で読み込める OLE コントロール プロパティを実装します。

[CCachedDataPathProperty](reference/ccacheddatapathproperty-class.md)<br/>
非同期で転送し、メモリ ファイルにキャッシュする OLE コントロール プロパティを実装します。

[COleCmdUI](reference/colecmdui-class.md)<br/>
アクティブなドキュメントが、コンテナーのユーザーインターフェイス (FileNew、Open、Print など) で発生したコマンドを受け取ることができるようにします。また、コンテナーは、アクティブなドキュメントのユーザーインターフェイスで生成されたコマンドを受け取ることができます。

[COleSafeArray](reference/colesafearray-class.md)<br/>
任意の型および次元の配列を操作します。

## <a name="see-also"></a>関連項目

[クラスの概要](class-library-overview.md)
