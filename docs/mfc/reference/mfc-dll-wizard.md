---
description: '詳細情報: MFC DLL ウィザード'
title: MFC DLL ウィザード
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.dll.overview
helpviewer_keywords:
- MFC DLLs [MFC], creating
- MFC DLL Wizard
- DLLs [MFC], MFC
- DLL wizard [MFC]
- MFC DLLs [MFC]
- DLLs [MFC], creating
ms.assetid: 4e936031-7e39-4f40-a295-42a09c5ff264
ms.openlocfilehash: 0f786255c22e644335c5154e0f14add59a2a418a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97219162"
---
# <a name="mfc-dll-wizard"></a>MFC DLL ウィザード

MFC DLL ウィザードを使用して MFC DLL プロジェクトを作成すると、組み込みの機能を備えた実用的なスターターアプリケーションが作成され、コンパイル時に [DLL](../../build/dlls-in-visual-cpp.md)の基本的な機能が実装されます。 MFC スタータープログラムには、C++ ソース (.cpp) ファイル、リソース (.rc) ファイル、およびプロジェクト (.vcxproj) ファイルが含まれています。 これらのスターターファイルで生成されるコードは、MFC に基づいています。 詳細については、Visual Studio でプロジェクトに対して生成される Readme.txt のファイルの詳細、および[MFC DLL ウィザードによって生成されるクラスと関数](../../mfc/reference/classes-and-functions-generated-by-the-mfc-dll-wizard.md)に関する説明を参照してください。

## <a name="overview"></a>概要

このウィザードページでは、作成する [MFC DLL プロジェクトの現在のアプリケーション設定](../../mfc/reference/application-settings-mfc-dll-wizard.md) について説明します。 既定では、プロジェクトは、追加設定のない通常の MFC DLL (MFC 共有) プロジェクトとして作成されます。

これらの既定値を変更するには、ウィザードの左側の列にある [ **アプリケーションの設定** ] をクリックし、MFC DLL ウィザードのそのページで変更を行います。

MFC DLL プロジェクトを作成した後、Visual C++ [コードウィザード](../../ide/adding-functionality-with-code-wizards-cpp.md)を使用して、プロジェクトにオブジェクトまたはコントロールを追加できます。

基本的な MFC DLL プロジェクトでは、次のタスクと拡張機能の種類を実行できます。

- [DLL からエクスポートする](../../build/exporting-from-a-dll.md)

- [実行可能ファイルを DLL にリンクする](../../build/linking-an-executable-to-a-dll.md)

- [DLL の初期化](../../build/run-time-library-behavior.md#initializing-a-dll)

## <a name="see-also"></a>関連項目

[Visual Studio プロジェクト - C++](../../build/creating-and-managing-visual-cpp-projects.md)<br/>
[[プロパティ ページ]](../../build/reference/property-pages-visual-cpp.md)<br/>
[コンパイラとビルドのプロパティの設定](../../build/working-with-project-properties.md)<br/>
[MFC クラス](../../mfc/reference/adding-an-mfc-class.md)<br/>
[メンバー関数の追加](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[インターフェイスの実装](../../ide/implementing-an-interface-visual-cpp.md)<br/>
