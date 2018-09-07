---
title: Active Template Library (ATL) の概念 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ATL, about ATL
ms.assetid: a3960991-4d76-4da5-9568-3fa7fde53ff4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3bb07807934dcc5c665f0058ef869f62f0b2d3ea
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43755425"
---
# <a name="active-template-library-atl-concepts"></a>ATL (Active Template Library) の概念

Active Template Library (ATL) は、小規模で高速のコンポーネント オブジェクト モデル (COM) オブジェクトを作成できるテンプレート ベースの C++ クラスのセットです。 ストックの実装、デュアル インターフェイス、列挙子の COM インターフェイスの標準的な接続ポイント、ティアオフ インターフェイス、および ActiveX コントロールをなど、キーの COM 機能用の特別なサポートしています。

ATL プログラミングの多くを実行する場合は、COM プログラミングを簡略化するように設計された Visual C .NET の新機能である属性の詳細についてはします。 詳細については、次を参照してください。[属性付きプログラミング](../windows/attributed-programming-concepts.md)します。

## <a name="in-this-section"></a>このセクションの内容

[ATL チュートリアル](../atl/active-template-library-atl-tutorial.md)  
コントロールの作成について説明し、プロセスで、ATL の基本事項をいくつかを示します。

[COM と ATL の概要](../atl/introduction-to-com-and-atl.md)  
コンポーネント オブジェクト モデル (COM) の背後にある主な概念が導入されています。 ここでは、ATL は、ときに使用する必要がありますも簡単に説明します。

[ATL COM オブジェクトの基礎](../atl/fundamentals-of-atl-com-objects.md)  
さまざまな ATL クラスとそれらのクラスを実装する方法の間の関係について説明します。

[デュアル インターフェイスと ATL](../atl/dual-interfaces-and-atl.md)  
ATL の観点からデュアル インターフェイスをについて説明します。

[ATL のコレクションと列挙子](../atl/atl-collections-and-enumerators.md)  
実装とコレクションと ATL で列挙子の作成について説明します

[複合コントロールの基本](../atl/atl-composite-control-fundamentals.md)  
複合コントロールを作成するための手順について説明します。 複合コントロールは、他の ActiveX コントロールまたは Windows のコントロールに含めることができる ActiveX コントロールの一種です。

[ATL コントロール コンテインメント : Q & A 集](../atl/atl-control-containment-faq.md)  
ATL. でコントロールをホストに関連する基本的な質問について説明します

[ATL COM プロパティ ページ](../atl/atl-com-property-pages.md)  
指定および COM プロパティ ページを実装する方法を示します。

[DHTML コントロールの ATL サポート](../atl/atl-support-for-dhtml-controls.md)  
DHTML コントロールの作成手順をについて説明します。

[ATL コネクション ポイント](../atl/atl-connection-points.md)  
接続ポイントの概要と ATL での実装方法について説明します。

[イベント処理と ATL](../atl/event-handling-and-atl.md)  
ATL を使用して COM イベントを処理するために必要な手順について説明します[IDispEventImpl](../atl/reference/idispeventimpl-class.md)と[IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md)クラス。

[ATL とフリー スレッド マーシャラー](../atl/atl-and-the-free-threaded-marshaler.md)  
フリー スレッド マーシャラー (FTM) を集計するのには、クラスは、ATL シンプル オブジェクト ウィザードのオプションの詳細を説明します。

[プロジェクトのスレッド モデルを指定します。](../atl/specifying-the-threading-model-for-a-project-atl.md)  
実行時のパフォーマンスに関連するプロジェクトでのスレッドの制御に使用できるマクロについて説明します。

[ATL モジュール クラス](../atl/atl-module-classes.md)  
ATL 7.0 の新しいモジュール クラスをについて説明します。 モジュール クラスが ATL で必要な基本機能を実装します。

[ATL サービス](../atl/atl-services.md)  
一連のサービスが実装されているときに発生するイベントについて説明します。 サービスの開発に関連する概念についても説明します。

[ATL ウィンドウ クラス](../atl/atl-window-classes.md)  
作成する方法、スーパークラスと ATL でウィンドウをサブクラス化について説明します ATL ウィンドウ クラスは、COM クラスではありません。

[ATL コレクション クラス](../atl/atl-collection-classes.md)  
配列を使用する方法について説明し、ATL のマップ

[ATL レジストリ コンポーネント (レジストラー)](../atl/atl-registry-component-registrar.md)  
ATL スクリプト構文と置き換え可能パラメーターをについて説明します。 レジストラーに静的にリンクを設定する方法も説明します。

[ATL および C ランタイム コードによるプログラミング](../atl/programming-with-atl-and-c-run-time-code.md)  
静的または動的に C ランタイム ライブラリ (CRT) へのリンクの利点について説明します。

[CComBSTR を使用したプログラミング](../atl/programming-with-ccombstr-atl.md)  
プログラミングする際の注意を必要とするいくつかの状況について説明します`CComBSTR`します。

[エンコーディングのリファレンス](../atl/atl-encoding-reference.md)  
関数と atlenc.h の関数で uuencode、16 進数などの一般的なインターネット標準の範囲と UTF8 でエンコードをサポートするマクロを提供します。

[ユーティリティのリファレンス](../atl/atl-utilities-reference.md)  
形式でパスと Url を操作するコードを提供[CPathT](../atl/reference/cpatht-class.md)と[CUrl](../atl/reference/curl-class.md)します。 スレッド プールでは、 [CThreadPool](../atl/reference/cthreadpool-class.md)、独自のアプリケーションで使用できます。 このコードは、atlpath.h および atlutil.h 記載されています。

## <a name="related-sections"></a>関連項目

[ATL のサンプル](../visual-cpp-samples.md)  
説明と ATL のサンプル プログラムへのリンクを提供します。

[ATL プロジェクトの作成](../atl/reference/creating-an-atl-project.md)  
ATL プロジェクト ウィザードについてを説明します。

[ATL コントロール ウィザード](../atl/reference/atl-control-wizard.md)  
クラスを追加する方法について説明します。

[属性付きプログラミング](../windows/attributed-programming-concepts.md)  
属性を使用して、COM プログラミングの詳細なトピックへのリンクの一覧を簡略化するには、概要を示します。

[ATL のクラスの概要](../atl/atl-class-overview.md)  
参照情報と ATL クラスへのリンクを提供します。

