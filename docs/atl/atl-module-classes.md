---
title: ATL モジュール クラス
ms.date: 11/04/2016
helpviewer_keywords:
- CComModule class, what's changed
- ATL, module classes
- module classes
ms.assetid: fd75382d-c955-46ba-a38e-37728b7fa00f
ms.openlocfilehash: 2b72cac0da06b70a40e01fcc75da52f1678f3f64
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317368"
---
# <a name="atl-module-classes"></a>ATL モジュール クラス

このトピックでは、ATL 7.0 で新しく追加されたモジュール クラスについて説明します。

## <a name="ccommodule-replacement-classes"></a>置換クラス

以前のバージョンの ATL が使用されました`CComModule`。 ATL 7.0`CComModule`では、機能はいくつかのクラスに置き換えられます。

- [カトルベースモジュール](../atl/reference/catlbasemodule-class.md)ATL を使用するほとんどのアプリケーションで必要な情報が含まれます。 モジュールとリソース インスタンスの HINSTANCE が含まれています。

- [カトルコムモジュール](../atl/reference/catlcommodule-class.md)ATL の COM クラスで必要な情報を格納します。

- [カトルウィンモジュール](../atl/reference/catlwinmodule-class.md)ATL のウィンドウ クラスで必要な情報を格納します。

- [モジュール](../atl/reference/catldebuginterfacesmodule-class.md)インターフェイスのデバッグのサポートが含まれています。

- [カトルモジュール](../atl/reference/catlmodule-class.md)次`CAtlModule`の派生クラスは、特定のアプリケーションの種類に必要な情報を含むカスタマイズされます。 これらのクラスのほとんどのメンバーは、オーバーライドできます。

  - [をクリックします。](../atl/reference/catldllmodulet-class.md)DLL アプリケーションで使用されます。 標準エクスポート用のコードを提供します。

  - [カトルエクセスト](../atl/reference/catlexemodulet-class.md)EXE アプリケーションで使用されます。 EXE で必要なコードを提供します。

  - [サービスモジュール](../atl/reference/catlservicemodulet-class.md)Windows NT および Windows 2000 サービスの作成に関するサポートを提供します。

`CComModule`下位互換性のために引き続き使用できます。

## <a name="reasons-for-distributing-ccommodule-functionality"></a>CCom モジュール機能を配布する理由

の機能は`CComModule`、次の理由により、いくつかの新しいクラスに配布されました。

- 機能を細かく`CComModule`します。

   COM、ウィンドウ、インターフェイスデバッグ、およびアプリケーション固有の (DLL または EXE) 機能のサポートは、別のクラスで行われます。

- これらの各モジュールのグローバル インスタンスを自動的に宣言します。

   必要なモジュール クラスのグローバル インスタンスがプロジェクトにリンクされます。

- Init メソッドと Term メソッドを呼び出す必要がなくなります。

   Init メソッドと Term メソッドは、モジュール クラスのコンストラクターとデストラクターに移動しました。Init と Term を呼び出す必要がなくなりました。

## <a name="see-also"></a>関連項目

[概念](../atl/active-template-library-atl-concepts.md)<br/>
[クラスの概要](../atl/atl-class-overview.md)
