---
description: '詳細情報: ATL モジュールクラス'
title: ATL モジュール クラス
ms.date: 11/04/2016
helpviewer_keywords:
- CComModule class, what's changed
- ATL, module classes
- module classes
ms.assetid: fd75382d-c955-46ba-a38e-37728b7fa00f
ms.openlocfilehash: 16c38a6a38f4179e5846a445bd9573e7dc4500f5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97163302"
---
# <a name="atl-module-classes"></a>ATL モジュール クラス

このトピックでは、ATL 7.0 で新しく追加されたモジュールクラスについて説明します。

## <a name="ccommodule-replacement-classes"></a>CComModule 置換クラス

以前のバージョンの ATL が使用されて `CComModule` います。 ATL 7.0 で `CComModule` は、機能はいくつかのクラスに置き換えられています。

- [CAtlBaseModule](../atl/reference/catlbasemodule-class.md) ATL を使用するほとんどのアプリケーションで必要な情報が含まれています。 モジュールとリソースインスタンスの HINSTANCE が含まれています。

- [CAtlComModule](../atl/reference/catlcommodule-class.md) ATL の COM クラスに必要な情報を格納します。

- [CAtlWinModule](../atl/reference/catlwinmodule-class.md) ATL のウィンドウクラスに必要な情報を格納します。

- [CAtlDebugInterfacesModule](../atl/reference/catldebuginterfacesmodule-class.md) インターフェイスデバッグのサポートが含まれています。

- [CAtlModule](../atl/reference/catlmodule-class.md) 次の `CAtlModule` 派生クラスは、特定のアプリケーションの種類で必要な情報を含むようにカスタマイズされています。 これらのクラスのほとんどのメンバーはオーバーライドできます。

  - [Catldllmodulet](../atl/reference/catldllmodulet-class.md) DLL アプリケーションで使用されます。 標準のエクスポートのコードを提供します。

  - [CAtlExeModuleT](../atl/reference/catlexemodulet-class.md) EXE アプリケーションで使用されます。 EXE で必要なコードを提供します。

  - [CAtlServiceModuleT](../atl/reference/catlservicemodulet-class.md) Windows NT および Windows 2000 サービスを作成するためのサポートを提供します。

`CComModule` は、旧バージョンとの互換性のために引き続き利用できます。

## <a name="reasons-for-distributing-ccommodule-functionality"></a>CComModule 機能を配布する理由

の機能は、 `CComModule` 次の理由により、いくつかの新しいクラスに配布されました。

- 機能をきめ細かく作成 `CComModule` します。

   COM、ウィンドウ、インターフェイスデバッグ、アプリケーション固有の (DLL または EXE) 機能のサポートは、別のクラスに含まれるようになりました。

- これらの各モジュールのグローバルインスタンスを自動的に宣言します。

   必須のモジュールクラスのグローバルインスタンスがプロジェクトにリンクされます。

- Init メソッドと Term メソッドを呼び出す必要がないようにします。

   Init メソッドと Term メソッドは、モジュールクラスのコンストラクターとデストラクターに移動しました。Init と Term を呼び出す必要がなくなりました。

## <a name="see-also"></a>関連項目

[概念](../atl/active-template-library-atl-concepts.md)<br/>
[クラスの概要](../atl/atl-class-overview.md)
