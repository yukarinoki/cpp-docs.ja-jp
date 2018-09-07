---
title: サードパーティ ライブラリの移植 | Microsoft ドキュメント
ms.custom: ''
ms.date: 01/10/2017
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- 3rd-party libraries
- vspkg
ms.assetid: b055ed20-8a9e-45b2-ac2a-e3d94271c009
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3e1edc9e4a6172b3ac55e7a8bc9b21cdc571774d
ms.sourcegitcommit: e9ce38decc9f986edab5543de3464b11ebccb123
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2018
ms.locfileid: "42578410"
---
# <a name="porting-third-party-libraries"></a>サード パーティ ライブラリの移植

プロジェクトを Visual C++ の現在のバージョンにアップグレードする場合は、プロジェクトで使用されているライブラリもアップグレードする必要があります。これにより、ライブラリとプロジェクトは、同じバージョンおよび種類のコンパイラでビルドされます。 詳細については、「[アップグレード時の潜在的な問題の概要](overview-of-potential-upgrade-issues-visual-cpp.md)」 を参照してください。 

## <a name="introducing-vcpkg"></a>vcpkg の概要

これまでは、サードパーティ ライブラリの検索とアップグレードが困難な作業となる場合がありました。 サードパーティ製の C++ オープンソース ライブラリの取得とリビルドを簡単にするために、Visual C++ チームは、**VC++ パッケージ ツール**または **vcpkg** と呼ばれるコマンドライン ツールを作成しました。 vcpkg には、多くの一般的な C++ オープンソース ライブラリの、検索可能なカタログがあります。 vcpkg コマンドラインから、カタログ内の任意のライブラリを直接インストールすることができます。 ライブラリをインストールすると、vcpkg によってコンピューターにディレクトリ ツリーが作成され、このフォルダー内に .h、.lib、およびバイナリが追加されます。 このフォルダーは、コンパイル コマンドラインで使用することも、vcpkg integrate install コマンドによって Visual Studio 2015 以降に統合することもできます。 ライブラリの場所を統合すると、Visual Studio でそのライブラリの場所を検索したり、作成した新しいプロジェクトに追加したりすることができます。 ライブラリを使用するには、それを `#include` するだけです。あとは、Visual Studio が自動的にプロジェクト設定への .lib パスを追加し、ソリューション フォルダーに dll をコピーします。 詳細については、「[vcpkg: C++ 用のパッケージ マネージャー](../vcpkg.md)」を参照してください。

## <a name="reporting-issues"></a>レポートの問題

**vcpkg** カタログ内に目的のライブラリが存在しない場合は、[GitHub リポジトリ](https://github.com/Microsoft/vcpkg/issues)に掲載されている問題点を参照できます。コミュニティおよび Visual C++ チームは、内容を確認することで、該当するライブラリのポート ファイルを作成できる可能性があります。

サードパーティ独自のライブラリ (非オープン ソース) の場合、ライブラリの製造元に問い合わせることをお勧めします。 ただし、使用する独自仕様の lib のうちアクセスできないものがあれば、どちらの lib であるかをお知らせください (連絡先は vcupgrade@microsoft.com です)。
  
## <a name="see-also"></a>参照  

[Visual C++ 移植とアップグレードのガイド](visual-cpp-porting-and-upgrading-guide.md)