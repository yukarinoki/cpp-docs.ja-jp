---
title: MFC マクロとグローバル |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- MFC, global functions and variables
- MFC, macros
- global functions, MFC
- macros, MFC
- global functions [MFC]
- global variables, MFC
- Afx naming convention
- macros
ms.assetid: add4e33f-0e62-4d27-be14-896cb8675d22
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 189e3f272d679030c11fcd11ca4760f59944faeb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="mfc-macros-and-globals"></a>MFC マクロとグローバル
MFC (Microsoft Foundation Class) ライブラリは、(1) MFC クラス、(2) マクロおよびグローバル関数とグローバル変数の 2 つの主要な分野で構成されます。 クラスのメンバーではない関数や変数は、グローバル関数またはグローバル変数です。  
  
 MFC ライブラリと ATL (Active Template Library) は文字列変換マクロを共有します。 詳細については、次を参照してください。[文字列変換マクロ](../../atl/reference/string-conversion-macros.md)、ATL マニュアルを参照します。  
  
 MFC のマクロ、グローバル関数、およびグローバル変数には、次の機能が用意されています。  
  
## <a name="general-mfc"></a>汎用 MFC  
  
-   [データ型](data-types-mfc.md)  
  
-   [MFC クラス オブジェクトの型キャスト](type-casting-of-mfc-class-objects.md)  
  
-   [ランタイム オブジェクト モデル サービス](run-time-object-model-services.md)  
  
-   [診断サービス](diagnostic-services.md)  
  
-   [例外の処理](exception-processing.md)  
  
-   [CString の書式指定とメッセージ ボックスの表示](cstring-formatting-and-message-box-display.md)  
  
-   [メッセージ マップします。](message-map-macros-mfc.md)  

-   [デリゲートとインターフェイス マップ](delegate-and-interface-maps.md)

-   [モジュールと DLL](extension-dll-macros.md)
  
-   [アプリケーションの情報と管理](application-information-and-management.md)  
  
-   [標準コマンド id とウィンドウ Id](standard-command-and-window-ids.md)  
  
-   [コレクション クラスのヘルパー](collection-class-helpers.md)  
  
-   [灰色とディザリングされたビットマップ関数](gray-and-dithered-bitmap-functions.md)  
  
-   [標準的なダイアログ データ エクス (チェンジ DDX) のルーチン](standard-dialog-data-exchange-routines.md)  
  
-   [標準的なダイアログ データ バリデーション (DDV) ルーチン](standard-dialog-data-validation-routines.md)  
  
-   [AFX メッセージ](afx-messages.md)  
  
-   [ツール バー コントロールのスタイル](toolbar-control-styles.md)  
  
-   [CMFCImagePaintArea::IMAGE_EDIT_MODE 列挙体](cmfcimagepaintarea-image-edit-mode-enumeration.md)  

  
## <a name="database"></a>データベース  
  
-   [レコード フィールド エクス チェンジ (RFX) 関数](record-field-exchange-functions.md)と[バルク レコード フィールド エクス チェンジ (bulk RFX) 関数](record-field-exchange-functions.md)MFC ODBC クラス  
  
-   [レコード フィールド エクス (チェンジ DFX) 関数](record-field-exchange-functions.md)MFC DAO クラス  
  
-   [CRecordView と CDaoRecordView のダイアログ データ エクス (チェンジ DDX) 関数](dialog-data-exchange-functions-for-crecordview-and-cdaorecordview.md)(MFC ODBC と DAO クラス)  
  
-   [OLE コントロールのダイアログ データ エクス (チェンジ DDX) 関数](dialog-data-exchange-functions-for-ole-controls.md)  
  
-   [マクロとグローバル オープン データベース コネクティビティ (ODBC) API 関数を直接呼び出すに役立つ](database-macros-and-globals.md)  
  
-   [DAO データベース エンジンの初期化と終了](dao-database-engine-initialization-and-termination.md)  
  
## <a name="internet"></a>インターネット  
  
-   [インターネット URL 解析用グローバル関数](internet-url-parsing-globals.md)  
  
## <a name="dhtml--dhtml-event-maps"></a>DHTML/DHTML のイベント マップ  
  
-   [DHTML ダイアログ データ エクス (チェンジ DDX) ヘルパー マクロ](ddx-dhtml-helper-macros.md)  
  
-   [DHTML イベント マップ](dhtml-event-maps.md)  
  
## <a name="ole"></a>OLE  
  
-   [OLE の初期化](ole-initialization.md)  
  
-   [アプリケーションの制御](application-control.md)  
  
-   [ディスパッチ マップ](dispatch-maps.md)  
  
 さらに、MFC には、呼び出される関数[AfxEnableControlContainer](ole-initialization.md#afxenablecontrolcontainer) OLE コントロールが完全にサポートする MFC 4.0 で開発したすべての OLE コンテナーを有効に埋め込まれていること。  
  
## <a name="ole-controls"></a>OLE コントロール  
  
-   [Variant パラメーター型の定数](variant-parameter-type-constants.md)  
  
-   [タイプ ライブラリ アクセス](type-library-access.md)  
  
-   [プロパティ ページ](property-pages-mfc.md)  
  
-   [イベント マップします。](event-maps.md)  
  
-   [イベント シンク マップします。](event-sink-maps.md)  
  
-   [コネクション マップ](connection-maps.md)  
  
-   [OLE コントロールの登録](registering-ole-controls.md)  
  
-   [クラス ファクトリとライセンス](class-factories-and-licensing.md)  
  
-   [OLE コントロールの永続化](persistence-of-ole-controls.md)  
  
 このセクションの最初の部分では、上に示した各カテゴリについて簡単に説明し、カテゴリ内の各グローバル関数、グローバル変数、およびマクロの一覧を簡単な機能説明と共に示します。 次に、MFC ライブラリのグローバル関数、グローバル変数、およびマクロについて説明します。  
  
> [!NOTE]
>  グローバル関数の多くはプレフィックス "Afx" で始まります。ただし、ダイアログ データ エクスチェンジ (DDX) 関数や多くのデータベース関数など、一部に例外もあります。 すべてのグローバル変数はプリフィックス "afx" で始まります。 マクロは特定のプリフィックスでは始まりませんが、すべて大文字を使用します。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../mfc/class-library-overview.md)



