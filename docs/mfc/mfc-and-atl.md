---
title: MFC と ATL |Microsoft Docs
ms.custom: ''
ms.date: 01/24/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 31b1a3a8-4154-4c4a-af10-fafc23ecdc5c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e6533738100f68c1133e21e0fc8c537e1cd7d270
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46384261"
---
# <a name="mfc-and-atl"></a>MFC と ATL

Microsoft Foundation Classes (MFC) は Win32 上の C++ オブジェクト指向ラッパーを提供し、ネイティブ デスクトップ アプリケーションの迅速な開発を可能にします。 Active Template Library (ATL) は COM 開発を簡単にするラッパー ライブラリで、ActiveX コントロールを作成するためによく使用されます。

MFC や ATL プログラムは Visual Studio Community エディションか、それ以上のエディションで作成できます。 Express Edition は、MFC や ATL をサポートしません。

Visual Studio 2015 では、Visual C++ はオプションのコンポーネントです。また、MFC および ATL コンポーネントは Visual C++ のオプションのサブコンポーネントです。 Visual Studio の初回インストール時に、これらのコンポーネントを選択しなかった場合、MFC プロジェクトや ATL プロジェクトを初めて作成したり、開こうとしたときに、これらのコンポーネントをインストールするよう要求されます。

MFC と ATL が下のオプションのサブコンポーネントは Visual Studio 2017 以降では、 **C++ によるデスクトップ開発**Visual Studio インストーラー プログラムでのワークロード。 せず、MFC、ATL サポートをインストールできますか、MFC と ATL のサポート (MFC は、ATL によって異なります) を結合します。 ワークロードとコンポーネントの詳細については、次を参照してください。 [Visual Studio 2017 のインストール](/visualstudio/install/install-visual-studio)します。

## <a name="related-articles"></a>関連トピック

|タイトル|説明|
|-----------|-----------------|
|[MFC デスクトップ アプリケーション](../mfc/mfc-desktop-applications.md)|Microsoft Foundation Classes は Win32 上のオブジェクト指向のシン ラッパーを提供し、C++ の GUI アプリケーションの迅速な開発を可能にします。|
|[ATL COM デスクトップ コンポーネント](../atl/atl-com-desktop-components.md)|ATL は、クラス テンプレートおよびその他の使用のためのコンストラクトを提供し、C++ の COM オブジェクトの作成が簡単にします。|
|[ATL/MFC 共有クラス](../atl-mfc-shared/atl-mfc-shared-classes.md)|MFC および ATL で共有される [CStringT Class](../atl-mfc-shared/reference/cstringt-class.md) およびその他のクラスのためのリファレンス。|
|[リソース ファイルの操作](../windows/working-with-resource-files.md)|リソース エディターを使用して、文字列、画像、ダイアログ ボックスなどの UI リソースを編集できます。|
|[Visual C++](../visual-cpp-in-visual-studio.md)|MSDN ライブラリのすべての C++ コンテンツの親トピック。|