---
title: ATL モジュール クラス |Microsoft ドキュメント
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
ms.openlocfilehash: 777d81fbe1de48289863fda00591a5328b40cf4c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="atl-module-classes"></a>ATL モジュール クラス
このトピックでは、ATL 7.0 で新規に追加されたモジュールのクラスについて説明します。  
  
## <a name="ccommodule-replacement-classes"></a>CComModule 置換クラス  
 以前のバージョンのために使用する ATL`CComModule`です。 ATL 7.0 で`CComModule`機能がいくつかのクラスによって置き換えられます。  
  
-   [CAtlBaseModule](../atl/reference/catlbasemodule-class.md) ATL を使用するほとんどのアプリケーションで必要な情報が含まれています モジュールと、リソースのインスタンスの HINSTANCE を格納します。  
  
-   [CAtlComModule](../atl/reference/catlcommodule-class.md) ATL の COM クラスで必要な情報が含まれています  
  
-   [CAtlWinModule](../atl/reference/catlwinmodule-class.md) ATL の windowing クラスで必要な情報が含まれています  
  
-   [CAtlDebugInterfacesModule](../atl/reference/catldebuginterfacesmodule-class.md)インターフェイスのデバッグのサポートが含まれています。  
  
-   [不要](../atl/reference/catlmodule-class.md)次`CAtlModule`-特定のアプリケーションの種類で必要な情報を格納する派生クラスをカスタマイズします。 これらのクラスのほとんどのメンバーをオーバーライドすることができます。  
  
    -   [CAtlDllModuleT](../atl/reference/catldllmodulet-class.md) DLL アプリケーションで使用します。 標準のエクスポートのコードを提供します。  
  
    -   [CAtlExeModuleT](../atl/reference/catlexemodulet-class.md) EXE アプリケーションで使用します。 EXE に必要なコードを提供します。  
  
    -   [CAtlServiceModuleT](../atl/reference/catlservicemodulet-class.md) Windows NT と Windows 2000 サービスの作成をサポートします。  
  
 `CComModule` 旧バージョンとの互換性のために引き続き使用できます。  
  
## <a name="reasons-for-distributing-ccommodule-functionality"></a>CComModule 機能を配布する理由  
 機能`CComModule`をいくつかの新しいクラスに配布されて、次の理由の。  
  
-   機能を行う`CComModule`細分化されました。  
  
     COM、windowing、インターフェイスのデバッグ、およびアプリケーション固有 (DLL または EXE) の機能のサポートは、別個のクラスにはようになりました。  
  
-   これらの各モジュールのグローバル インスタンスを自動的に宣言します。  
  
     必要なモジュール クラスのグローバル インスタンスは、プロジェクトにリンクされます。  
  
-   Init と用語のメソッドを呼び出す必要があることを削除します。  
  
     Init と用語のメソッドに移動コンス トラクターとデストラクターのモジュールのクラスです。Init と用語を呼び出す必要はありません。  
  
## <a name="see-also"></a>関連項目  
 [概念](../atl/active-template-library-atl-concepts.md)   
 [クラスの概要](../atl/atl-class-overview.md)

