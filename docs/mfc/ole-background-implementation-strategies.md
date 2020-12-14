---
description: '詳細については、「OLE バックグラウンド: 実装方法」を参照してください。'
title: 'OLE の背景知識 : 実装の方法'
ms.date: 11/04/2016
helpviewer_keywords:
- OLE [MFC], development strategy
- OLE applications [MFC], implementing OLE
- applications [OLE], implementing OLE
ms.assetid: 0875ddae-99df-488c-82c6-164074a81058
ms.openlocfilehash: fe492adf755f9163586832f5c7aa7dfc5470349f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97275478"
---
# <a name="ole-background-implementation-strategies"></a>OLE の背景知識 : 実装の方法

アプリケーションによっては、OLE サポートを追加するための実装方法として、次の4つが考えられます。

- 新しいアプリケーションを作成しようとしています。

   この状況では、通常、最小限の作業が必要です。 MFC アプリケーションウィザードを実行し、[高度な機能] または [複合ドキュメントのサポート] を選択してスケルトンアプリケーションを作成します。 これらのオプションとその機能の詳細については、 [MFC EXE プログラムの作成](reference/mfc-application-wizard.md)に関する記事を参照してください。

- OLE をサポートしていない Microsoft Foundation Class ライブラリバージョン2.0 以降のプログラムが記述されています。

   前述のように、MFC アプリケーションウィザードを使用して新しいアプリケーションを作成し、新しいアプリケーションから既存のアプリケーションにコードをコピーして貼り付けます。 これは、サーバー、コンテナー、または自動アプリケーションに対して機能します。 この戦略の例については、「MFC [SCRIBBLE](../overview/visual-cpp-samples.md) サンプル」を参照してください。

- OLE バージョン1.0 サポートを実装する Microsoft Foundation Class ライブラリプログラムがあります。

   この変換方法については、「 [MFC テクニカルノート 41](tn041-mfc-ole1-migration-to-mfc-ole-2.md) 」を参照してください。

- Microsoft Foundation Classes を使用して記述されていないアプリケーションがあり、OLE サポートが実装されているか、実装されていない可能性があります。

   この状況では、ほとんどの作業が必要です。 1つ目の方法として、最初の方法と同じように新しいアプリケーションを作成し、既存のコードをコピーして貼り付けます。 既存のコードが C で記述されている場合は、C++ コードとしてコンパイルできるように、コードを変更する必要がある場合があります。 C コードで Windows API を呼び出す場合は、Microsoft Foundation クラスを使用するように変更する必要はありません。 この方法では、バージョン2.0 以上の Microsoft Foundation Classes によって使用されるドキュメント/ビューアーキテクチャをサポートするために、プログラムの再構築が必要になる可能性があります。 このアーキテクチャの詳細については、「 [テクニカルノート 25](tn025-document-view-and-frame-creation.md)」を参照してください。

戦略を決定したら、 [コンテナー](containers.md) または [サーバー](servers.md) の記事 (記述するアプリケーションの種類によって異なります) を読むか、サンプルプログラムまたはその両方を確認する必要があります。 MFC OLE サンプル [OCLIENT](../overview/visual-cpp-samples.md) および [HIERSVR](../overview/visual-cpp-samples.md) は、コンテナーとサーバーのさまざまな側面をそれぞれ実装する方法を示しています。 これらの記事のさまざまな点で、これらのサンプルの特定の機能が、説明されている手法の例として参照されます。

## <a name="see-also"></a>関連項目

[OLE の背景](ole-background.md)<br/>
[コンテナー: コンテナーの実装](containers-implementing-a-container.md)<br/>
[サーバー: サーバーの実装](servers-implementing-a-server.md)<br/>
[MFC アプリケーションウィザード](reference/mfc-application-wizard.md)
