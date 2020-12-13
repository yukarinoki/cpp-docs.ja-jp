---
description: 詳細については、サードパーティ製ライブラリの移植に関するページを参照してください。
title: サードパーティ ライブラリの移植
ms.date: 10/29/2019
helpviewer_keywords:
- 3rd-party libraries
- vspkg
ms.assetid: b055ed20-8a9e-45b2-ac2a-e3d94271c009
ms.openlocfilehash: cead058a6d3995a77726bc995996871eba29047f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331237"
---
# <a name="porting-third-party-libraries"></a>サード パーティ ライブラリの移植

プロジェクトを Visual Studio 2013 以前の Visual C++ の現在のバージョンにアップグレードする場合は、プロジェクトで使用されているすべてのライブラリをアップグレードして、ライブラリとプロジェクトが同じバージョンとフレーバーでビルドされるようにする必要があります。 ライブラリのソースコードにアクセスできず、そのライブラリが vcpkg で使用できない場合は、ライブラリのベンダから更新されたバイナリを取得する必要があります。 (詳細については、「 [アップグレードに関する潜在的な問題の概要](overview-of-potential-upgrade-issues-visual-cpp.md)」を参照してください)。

アプリケーションを Visual Studio 2015 または Visual Studio 2017 から Visual Studio 2019 にアップグレードする場合、依存関係をアップグレードする必要はありません。これは、3つのバージョンで生成されるコードがバイナリ互換であるためです。 詳細については、「 [Visual studio 2015 と Visual studio 2019 間の C++ バイナリ互換性](binary-compat-2015-2017.md)」を参照してください。

## <a name="vcpkg-for-open-source-libraries"></a>オープンソースライブラリの vcpkg

これまでは、サードパーティ ライブラリの検索とアップグレードが困難な作業となる場合がありました。 C++ サードパーティのオープンソースライブラリを簡単に取得および再構築できるように、Visual C++ チームは **VC + + パッケージ化ツール** または **vcpkg** と呼ばれるコマンドラインツールを作成しました。 vcpkg には、多くの一般的な C++ オープンソース ライブラリの、検索可能なカタログがあります。 vcpkg コマンドラインから、カタログ内の任意のライブラリを直接インストールすることができます。 ライブラリをインストールすると、vcpkg によってコンピューターにディレクトリ ツリーが作成され、このフォルダー内に .h、.lib、およびバイナリが追加されます。 このフォルダーは、コンパイル コマンドラインで使用することも、vcpkg integrate install コマンドによって Visual Studio 2015 以降に統合することもできます。 ライブラリの場所を統合すると、Visual Studio でそのライブラリの場所を検索したり、作成した新しいプロジェクトに追加したりすることができます。 ライブラリを使用するには、それを `#include` するだけです。あとは、Visual Studio が自動的にプロジェクト設定への .lib パスを追加し、ソリューション フォルダーに dll をコピーします。 詳細については、[vcpkg: C++ 用のパッケージ マネージャー](../build/vcpkg.md)に関する記事を参照してください。

## <a name="reporting-issues"></a>問題の報告

オープンソースライブラリが **vcpkg** カタログに存在しない場合は、 [GitHub リポジトリ](https://github.com/Microsoft/vcpkg/issues) で問題を開くことができます。このリポジトリでは、コミュニティと Visual C++ チームが参照でき、このライブラリのポートファイルが作成される可能性があります。

## <a name="see-also"></a>関連項目

[Visual C++ 移植とアップグレードのガイド](visual-cpp-porting-and-upgrading-guide.md)
