---
description: '詳細情報: ATL プロジェクトウィザード'
title: ATL プロジェクト ウィザード
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.atl.com.overview
helpviewer_keywords:
- ATL projects, creating
- ATL Project Wizard
ms.assetid: 564d2aaf-5b8e-4c2a-a925-ca40a283ea34
ms.openlocfilehash: a254447d0590abd3d68090dac04c3b6134f94b19
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158674"
---
# <a name="atl-project-wizard"></a>ATL プロジェクト ウィザード

Active Template Library (ATL) は、小さな COM オブジェクトと高速 COM オブジェクトの記述を簡略化する、テンプレートベースの C++ クラスのセットです。 ATL プロジェクトウィザードでは、COM オブジェクトを格納する構造を持つプロジェクトが作成されます。

## <a name="overview"></a>概要

このウィザードページでは、作成する [ATL プロジェクトの現在のアプリケーション設定](../../atl/reference/application-settings-atl-project-wizard.md) について説明します。 既定では、プロジェクトには次の設定があります。

- ダイナミックリンクライブラリは、サーバーが DLL であるため、インプロセスサーバーであることを指定します。

- 属性は、プロジェクトが属性を使用することを指定します。

これらの既定値を変更するには、ウィザードの左側の列にある [ **アプリケーションの設定** ] をクリックし、ATL プロジェクトウィザードのそのページで変更を行います。

文字セットの選択やリンクの既定値など、既定のプロジェクト設定については、「 [既定の ATL プロジェクト構成](../../atl/reference/default-atl-project-configurations.md)」を参照してください。

ATL プロジェクトを作成した後、Visual C++ [コードウィザード](../../ide/adding-functionality-with-code-wizards-cpp.md)を使用して、プロジェクトにオブジェクトまたはコントロールを追加できます。 コードウィザードを使用して、基本的な ATL プロジェクトに対して次の種類の拡張機能を作成できます。

- [ATL プロジェクトにオブジェクトとコントロールを追加する](../../atl/reference/adding-objects-and-controls-to-an-atl-project.md)

- [ATL プロジェクトでの新しいインターフェイスの追加](../../atl/reference/adding-a-new-interface-in-an-atl-project.md)

- [COM + 1.0 コンポーネントを ATL プロジェクトに追加する](../../atl/reference/adding-an-atl-com-plus-1-0-component.md)

また、ATL プロジェクトを作成および強化する場合は、次の作業を検討してください。

- [ATL オブジェクトを作成できないようにする](../../atl/reference/making-an-atl-object-noncreatable.md)

- [ATL プロジェクトのコンパイラを最適化する](../../atl/reference/specifying-compiler-optimization-for-an-atl-project.md)

[プロジェクトプロパティページで](../../build/reference/general-property-page-project.md)プロジェクトのプロパティ ( [CRT に静的にリンクするかどうか](../../atl/programming-with-atl-and-c-run-time-code.md)など) を指定できます。また、ATL プロジェクトの[ビルド構成](/visualstudio/ide/understanding-build-configurations)を設定することもできます。

## <a name="see-also"></a>関連項目

[Visual Studio プロジェクト - C++](../../build/creating-and-managing-visual-cpp-projects.md)<br/>
[Visual Studio の C++ プロジェクトの種類](../../build/reference/visual-cpp-project-types.md)<br/>
[ATL COM オブジェクトの基礎](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[ATL および C Run-Time コードを使用したプログラミング](../../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[チュートリアル](../../atl/active-template-library-atl-tutorial.md)
