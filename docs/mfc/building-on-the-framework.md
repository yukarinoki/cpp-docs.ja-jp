---
description: 詳細については、「フレームワークでのビルド」を参照してください。
title: フレームワークを使ったアプリケーションの作成
ms.date: 11/04/2016
helpviewer_keywords:
- application-specific classes [MFC]
- application framework [MFC], building applications
- applications [MFC]
- MFC, application development
ms.assetid: 883f0f19-866f-4221-8a3d-5607941dc8d0
ms.openlocfilehash: dd9423bb8cf80463631d6a39212db42ab94a67ce
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339788"
---
# <a name="building-on-the-framework"></a>フレームワークを使ったアプリケーションの作成

MFC フレームワークを使用してアプリケーションを構成する際の役割は、アプリケーション固有のソースコードを提供し、応答するメッセージとコマンドを定義することによってコンポーネントを接続することです。 C++ 言語と標準 C++ 手法を使用して、クラスライブラリによって提供されるクラスから独自のアプリケーション固有のクラスを派生させ、基底クラスの動作をオーバーライドおよび拡張します。

関連トピックでは、次の表に、通常従う操作の一般的な順序と、その役割とフレームワークの役割について説明します。

- [フレームワークを使用してアプリケーションをビルドするためのシーケンス](sequence-of-operations-for-building-mfc-applications.md)

- [OLE アプリケーションを作成するための一連の操作](sequence-of-operations-for-creating-ole-applications.md)

- [ActiveX コントロールを作成するための一連の操作](sequence-of-operations-for-creating-activex-controls.md)

- [データベースアプリケーションを作成するための一連の操作](sequence-of-operations-for-creating-database-applications.md)

ほとんどの場合、これらの表は、MFC アプリケーションを作成するための一連の手順として使用できます。ただし、一部の手順は代替オプションです。 たとえば、ほとんどのアプリケーションでは、いくつかの種類のビュークラスを使用できます。

## <a name="see-also"></a>関連項目

[MFC の一般的なトピック](general-mfc-topics.md)
