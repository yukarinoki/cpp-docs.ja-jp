---
title: OLE コントロール クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.ole
dev_langs:
- C++
helpviewer_keywords:
- ActiveX classes [MFC]
- custom controls [MFC], classes
- ActiveX controls [MFC], OLE control classes
- ActiveX control classes [MFC]
- OLE controls [MFC], classes
- OLE control classes [MFC]
- reusable component classes [MFC]
ms.assetid: 96495ec3-319e-4163-b839-1af0428ed9dd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5dcbda85c33bab37babe5da861067d25cf31e32c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33355358"
---
# <a name="ole-control-classes"></a>OLE コントロール クラス
これらは、OLE コントロールを作成するときに使用する主なクラスです。 `COleControlModule` OLE コントロール モジュール内のクラスと同様に、 [CWinApp](../mfc/reference/cwinapp-class.md)アプリケーション内のクラスです。 各モジュールが 1 つまたは複数の OLE コントロールを実装します。これらのコントロールがによって表される`COleControl`オブジェクト。 これらのコントロールを使用して、コンテナーとの通信`CConnectionPoint`オブジェクト。  
  
 `CPictureHolder`と`CFontHolder`クラスは、画像やフォントなどの COM インターフェイスをカプセル化中に、`COlePropertyPage`と`CPropExchange`クラスを使用して、プロパティ ページおよびコントロールのプロパティの永続化を実装できます。  
  
 [COleControlModule](../mfc/reference/colecontrolmodule-class.md)  
 置換、 `CWinApp` OLE コントロール モジュールのクラスです。 派生して、 `COleControlModule` OLE コントロール モジュール オブジェクトを開発するクラス。 OLE コントロールのモジュールを初期化するためのメンバー関数を提供します。  
  
 [COleControl](../mfc/reference/colecontrol-class.md)  
 派生して、 `COleControl` OLE コントロールを開発するクラス。 派生`CWnd`、このクラスは、Windows ウィンドウ オブジェクトのすべての機能、およびイベントを発生させると、メソッドとプロパティをサポートする権限などの追加 OLE 固有の機能を継承します。  
  
 [関数](../mfc/reference/cconnectionpoint-class.md)  
 `CConnectionPoint`クラスは、特殊な接続ポイントと呼ばれるその他の OLE オブジェクトと通信するために使用されるインターフェイスを定義します。 接続ポイントは、イベントを発生させるなど、他のオブジェクトのアクションを開始して、変更通知が送信インターフェイスを実装します。  
  
 [CPictureHolder](../mfc/reference/cpictureholder-class.md)  
 Windows 画像オブジェクトの機能をカプセル化し、 `IPicture` COM インターフェイスです。 OLE コントロールのカスタム Picture プロパティを実装するために使用します。  
  
 [CFontHolder](../mfc/reference/cfontholder-class.md)  
 Windows のフォント オブジェクトの機能をカプセル化し、 `IFont` COM インターフェイスです。 OLE コントロールのストック フォント プロパティを実装するために使用します。  
  
 [COlePropertyPage](../mfc/reference/colepropertypage-class.md)  
 ダイアログ ボックスのようなグラフィカル インターフェイスで制御する OLE のプロパティを表示します。  
  
 [CPropExchange](../mfc/reference/cpropexchange-class.md)  
 OLE コントロールのプロパティの永続性の実装をサポートしています。 に似て[CDataExchange](../mfc/reference/cdataexchange-class.md)  ダイアログ ボックス。  
  
 [CMonikerFile](../mfc/reference/cmonikerfile-class.md)  
 モニカー、または文字列形式にはモニカーには、モニカーの名前をストリームに同期的にバインドします。  
  
 [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md)  
 同じように動作`CMonikerFile`。 ただし、バインドされているモニカーに非同期的にモニカーの名前のストリームにします。  
  
 [関数](../mfc/reference/cdatapathproperty-class.md)  
 非同期で読み込める OLE コントロール プロパティを実装します。  
  
 [プロパティ](../mfc/reference/ccacheddatapathproperty-class.md)  
 非同期で転送し、メモリ ファイルにキャッシュする OLE コントロール プロパティを実装します。  
  
 [COleCmdUI](../mfc/reference/colecmdui-class.md)  
 Active ドキュメント コンテナーのユーザー インターフェイス (という名前、開く、印刷、およびなど) で発生するコマンドを受信をでき、アクティブなドキュメントのユーザー インターフェイスで発生するコマンドを受信するためのコンテナーです。  
  
 [COleSafeArray](../mfc/reference/colesafearray-class.md)  
 任意の型および次元の配列で動作します。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../mfc/class-library-overview.md)

