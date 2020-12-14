---
description: 詳細については、「MFC マクロとグローバル」を参照してください。
title: MFC マクロとグローバル
ms.date: 11/04/2016
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
ms.openlocfilehash: 9e3d3acd74d1cf6db5856432cdefd632e36185f3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97219149"
---
# <a name="mfc-macros-and-globals"></a>MFC マクロとグローバル

MFC (Microsoft Foundation Class) ライブラリは、(1) MFC クラス、(2) マクロおよびグローバル関数とグローバル変数の 2 つの主要な分野で構成されます。 クラスのメンバーではない関数や変数は、グローバル関数またはグローバル変数です。

MFC ライブラリと ATL (Active Template Library) は文字列変換マクロを共有します。 詳細については、ATL ドキュメントの「 [文字列変換マクロ](../../atl/reference/string-conversion-macros.md) 」を参照してください。

MFC のマクロ、グローバル関数、およびグローバル変数には、次の機能が用意されています。

## <a name="general-mfc"></a>汎用 MFC

- [データ型](data-types-mfc.md)

- [MFC クラス オブジェクトの型キャスト](type-casting-of-mfc-class-objects.md)

- [ランタイム オブジェクト モデル サービス](run-time-object-model-services.md)

- [診断サービス](diagnostic-services.md)

- [例外処理](exception-processing.md)

- [CString の書式指定とメッセージ ボックスの表示](cstring-formatting-and-message-box-display.md)

- [メッセージマップ](message-map-macros-mfc.md)

- [デリゲートとインターフェイスマップ](delegate-and-interface-maps.md)

- [モジュールと DLL](extension-dll-macros.md)

- [アプリケーションの情報と管理](application-information-and-management.md)

- [標準コマンド ID とウィンドウ ID](standard-command-and-window-ids.md)

- [コレクション クラスのヘルパー](collection-class-helpers.md)

- [淡色表示 (灰色) ビットマップ関数とディザリングされたビットマップ関数](gray-and-dithered-bitmap-functions.md)

- [標準的なダイアログ データ エクスチェンジ ルーチン](standard-dialog-data-exchange-routines.md)

- [標準的なダイアログ データ検証 (DDV) ルーチン](standard-dialog-data-validation-routines.md)

- [AFX メッセージ](afx-messages.md)

- [ツールバーコントロールスタイル](toolbar-control-styles.md)

- [CMFCImagePaintArea:: IMAGE_EDIT_MODE 列挙型](cmfcimagepaintarea-image-edit-mode-enumeration.md)

## <a name="database"></a>データベース

- MFC ODBC クラスの[レコードフィールドエクスチェンジ (RFX) 関数](record-field-exchange-functions.md)と[バルクレコードフィールドエクスチェンジ (bulk RFX) 関数](record-field-exchange-functions.md)

- MFC DAO クラス用の[レコードフィールドエクスチェンジ (DFX) 関数](record-field-exchange-functions.md)

- [CRecordView および CDaoRecordView 用のダイアログデータエクスチェンジ (DDX) 関数](dialog-data-exchange-functions-for-crecordview-and-cdaorecordview.md) (MFC ODBC および DAO クラス)

- [OLE コントロールのダイアログ データ エクスチェンジ (DDX) 関数](dialog-data-exchange-functions-for-ole-controls.md)

- [ODBC (Open Database Connectivity) API 関数を直接呼び出すマクロとグローバル](database-macros-and-globals.md)

- [DAO データベース エンジンの初期化と終了](dao-database-engine-initialization-and-termination.md)

## <a name="internet"></a>インターネット

- [インターネット URL 解析用グローバル](internet-url-parsing-globals.md)

## <a name="dhtml--dhtml-event-maps"></a>DHTML/DHTML のイベント マップ

- [DHTML dialog data exchange (DDX) ヘルパー マクロ](ddx-dhtml-helper-macros.md)

- [DHTML イベント マップ](dhtml-event-maps.md)

## <a name="ole"></a>OLE●ole○

- [OLE の初期化](ole-initialization.md)

- [[アプリケーションの制御]](application-control.md)

- [ディスパッチ マップ](dispatch-maps.md)

また、mfc には [AfxEnableControlContainer](ole-initialization.md#afxenablecontrolcontainer) という関数が用意されています。これを使用すると、mfc 4.0 で開発したすべての ole コンテナーで、埋め込み ole コントロールを完全にサポートできます。

## <a name="ole-controls"></a>OLE コントロール

- [Variant パラメーター型の定数](variant-parameter-type-constants.md)

- [タイプ ライブラリ アクセス](type-library-access.md)

- [プロパティページ](property-pages-mfc.md)

- [イベント マップ](event-maps.md)

- [イベント シンク マップ](event-sink-maps.md)

- [コネクション マップ](connection-maps.md)

- [OLE コントロールの登録](registering-ole-controls.md)

- [クラス ファクトリとライセンス](class-factories-and-licensing.md)

- [OLE コントロールの永続化](persistence-of-ole-controls.md)

このセクションの最初の部分では、上に示した各カテゴリについて簡単に説明し、カテゴリ内の各グローバル関数、グローバル変数、およびマクロの一覧を簡単な機能説明と共に示します。 次に、MFC ライブラリのグローバル関数、グローバル変数、およびマクロについて説明します。

> [!NOTE]
> グローバル関数の多くはプレフィックス "Afx" で始まります。ただし、ダイアログ データ エクスチェンジ (DDX) 関数や多くのデータベース関数など、一部に例外もあります。 すべてのグローバル変数はプリフィックス "afx" で始まります。 マクロは特定のプリフィックスでは始まりませんが、すべて大文字を使用します。

## <a name="see-also"></a>関連項目

[クラスの概要](../../mfc/class-library-overview.md)
