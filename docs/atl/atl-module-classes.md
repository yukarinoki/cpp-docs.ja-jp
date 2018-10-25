---
title: ATL モジュール クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CComModule class, what's changed
- ATL, module classes
- module classes
ms.assetid: fd75382d-c955-46ba-a38e-37728b7fa00f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7e067b1d72b80950b4ed33fbae8cac7333ac0438
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50083077"
---
# <a name="atl-module-classes"></a>ATL モジュール クラス

このトピックでは、ATL 7.0 で導入されたモジュールのクラスについて説明します。

## <a name="ccommodule-replacement-classes"></a>CComModule 置換クラス

以前のバージョンのために使用する ATL`CComModule`します。 ATL 7.0 で`CComModule`機能がいくつかのクラスによって置き換えられます。

- [CAtlBaseModule](../atl/reference/catlbasemodule-class.md) ATL を使用するほとんどのアプリケーションで必要な情報が含まれています モジュールとリソース インスタンスの HINSTANCE が含まれています。

- [CAtlComModule](../atl/reference/catlcommodule-class.md) ATL で COM クラスで必要な情報が含まれています

- [CAtlWinModule](../atl/reference/catlwinmodule-class.md) ATL のウィンドウ クラスに必要な情報が含まれています

- [CAtlDebugInterfacesModule](../atl/reference/catldebuginterfacesmodule-class.md)のインターフェイス デバッグのサポートが含まれています。

- [CAtlModule](../atl/reference/catlmodule-class.md)次`CAtlModule`-特定のアプリケーションの種類で必要な情報を格納する派生クラスをカスタマイズします。 これらのクラスのほとんどのメンバーをオーバーライドできます。

   - [CAtlDllModuleT](../atl/reference/catldllmodulet-class.md) DLL アプリケーションで使用します。 標準エクスポートのコードを提供します。

   - [CAtlExeModuleT](../atl/reference/catlexemodulet-class.md) EXE アプリケーションで使用します。 EXE で必要なコードを提供します。

   - [CAtlServiceModuleT](../atl/reference/catlservicemodulet-class.md) Windows NT、Windows 2000 のサービスを作成サポートを提供します。

`CComModule` 旧バージョンとの互換性のために引き続き使用できます。

## <a name="reasons-for-distributing-ccommodule-functionality"></a>CComModule 機能を配布する理由

機能`CComModule`次の理由をいくつかの新しいクラスに分散されました。

- 機能`CComModule`細分化されました。

   COM、ウィンドウ、インターフェイスは、次のデバッグ、およびアプリケーション固有 (DLL または EXE) の機能のサポートは、別のクラスはようになりました。

- これらの各モジュールのグローバル インスタンスを自動的に宣言します。

   必要なモジュールのクラスのグローバル インスタンスは、プロジェクトにリンクします。

- Init と用語のメソッドを呼び出す必要があることを削除します。

   Init と用語のメソッドが、モジュール クラスのコンス トラクターとデストラクターに移動します。Init と用語をコールする必要が不要になったです。

## <a name="see-also"></a>関連項目

[概念](../atl/active-template-library-atl-concepts.md)<br/>
[クラスの概要](../atl/atl-class-overview.md)

