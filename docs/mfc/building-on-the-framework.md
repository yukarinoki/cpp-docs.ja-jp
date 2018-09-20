---
title: フレームワークでの構築 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- application-specific classes [MFC]
- application framework [MFC], building applications
- applications [MFC]
- MFC, application development
ms.assetid: 883f0f19-866f-4221-8a3d-5607941dc8d0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4ca0ebd9bf03df8725c14df8d2aca1f7858b7b65
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46396182"
---
# <a name="building-on-the-framework"></a>フレームワークを使ったアプリケーションの作成

MFC フレームワークとアプリケーションの構成でのロールは、アプリケーション固有のソース コードを指定して、どのようなメッセージと応答するコマンドを定義することで、コンポーネントを接続するには。 C++ 言語および標準的な C++ 手法を使用して、クラス ライブラリで指定されているから、独自のアプリケーション固有のクラスを派生およびをオーバーライドし、基本クラスの動作を追加します。

関連のトピックでは、次の表は、次の通常操作とフレームワークの役割とお客様の責任の一般的な手順を示します。

- [フレームワークとアプリケーションを構築するためのシーケンス](../mfc/sequence-of-operations-for-building-mfc-applications.md)

- [OLE アプリケーションの作成手順](../mfc/sequence-of-operations-for-creating-ole-applications.md)

- [ActiveX コントロールの作成手順](../mfc/sequence-of-operations-for-creating-activex-controls.md)

- [データベース アプリケーションの作成手順](../mfc/sequence-of-operations-for-creating-database-applications.md)

ほとんどの場合、別のオプションは一部の手順は、MFC アプリケーションを作成するための手順のシーケンスとしてこれらのテーブルをフォローできます。 たとえば、ほとんどのアプリケーションは、使用できるいくつかの型からビュー クラスの 1 つの型を使用します。

## <a name="see-also"></a>関連項目

[MFC の一般的なトピック](../mfc/general-mfc-topics.md)

