---
description: '詳細情報: C/C++ プログラムのマニフェスト生成についての理解'
title: C/C++ プログラムのマニフェスト生成についての理解
ms.date: 11/04/2016
helpviewer_keywords:
- manifests [C++]
ms.assetid: a1f24221-5b09-4824-be48-92eae5644b53
ms.openlocfilehash: 78169dd6d8185e1ae8470dea93ab145fc05dbc7b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97277272"
---
# <a name="understanding-manifest-generation-for-cc-programs"></a>C/C++ プログラムのマニフェスト生成についての理解

[マニフェスト](/windows/win32/sbscs/manifests)は XML ドキュメントであり、外部 XML ファイルか、アプリケーションまたはアセンブリの内部に埋め込まれたリソースになります。 [分離アプリケーション](/windows/win32/SbsCs/isolated-applications)のマニフェストは、アプリケーションが実行時にバインドする共有 side-by-side アセンブリの名前およびバージョンの管理に使用されます。 side-by-side アセンブリのマニフェストによって、名前、バージョン、リソース、その他のアセンブリに対するその依存関係が指定されます。

分離アプリケーションまたは side-by-side アセンブリには 2 つの方法でマニフェストを作成できます。 まず、アセンブリの作成者が規則と名前付け要件に従い、マニフェストを手動で作成できます。 あるいは、プログラムが CRT、MFC、ATL など、Visual C++ アセンブリにのみ依存している場合、マニフェストはリンカーで自動的に生成できます。

Visual C++ ライブラリのヘッダーにはアセンブリ情報が含まれます。ライブラリがアプリケーション コードに含まれるとき、このアセンブリ情報は、最終バイナリのマニフェストを形成する目的で、リンカーによって使用されます。 リンカーによってバイナリ内にマニフェスト ファイルが埋め込まれることはありません。リンカーでは、外部ファイルとしてのみマニフェストを生成できます。 外部ファイルとしてマニフェストを用意することは、シナリオによってはうまく機能しない場合があります。 たとえば、プライベート アセンブリにはマニフェストを埋め込むことが推奨されています。 nmake を使用してコードをビルドするなどのコマンド ライン ビルドでは、マニフェストはマニフェスト ツールで埋め込むことができます。詳細については、「[コマンド ラインでのマニフェスト生成](manifest-generation-at-the-command-line.md)」を参照してください。 Visual Studio でビルドするとき、 **[プロジェクト プロパティ]** ダイアログでマニフェスト ツールにプロパティを設定することでマニフェストを埋め込むことができます。「[Visual Studio でのマニフェスト生成](manifest-generation-in-visual-studio.md)」を参照してください。

## <a name="see-also"></a>関連項目

[分離アプリケーションおよび side-by-side アセンブリの概念](concepts-of-isolated-applications-and-side-by-side-assemblies.md)<br/>
[C/C++ 分離アプリケーションおよび side-by-side アセンブリのビルド](building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)
