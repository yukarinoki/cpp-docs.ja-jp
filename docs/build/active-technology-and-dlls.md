---
title: Active テクノロジと DLL
ms.date: 11/04/2016
helpviewer_keywords:
- in-process server DLLs
- Automation [C++], DLLs
- DLLs [C++], Active Technology
- Active technology [C++]
- MFC DLLs [C++], Active Technology
ms.assetid: 3ed27f8d-164a-4562-ad61-9f2333404cc7
ms.openlocfilehash: f67fb9548601ac705ceda08d20d3049f0bf1e0a5
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221005"
---
# <a name="active-technology-and-dlls"></a>Active テクノロジと DLL

Active テクノロジでは、DLL 内にオブジェクト サーバーを完全に実装できます。 この種類のサーバーは、インプロセス サーバーと呼ばれます。 MFC では、ビジュアル編集のすべての機能でインプロセス サーバーを完全にはサポートしていません。これは主に、コンテナーのメイン メッセージ ループにサーバーをフックさせる方法が Active テクノロジにないためです。 MFC は、アクセラレータ キーとアイドル時間の処理を処理するために、コンテナー アプリケーションのメッセージ ループにアクセスする必要があります。

オートメーション サーバーを記述していて、ご自分のサーバーにユーザー インターフェイスがない場合は、ご自分のサーバーをインプロセス サーバーとして作成し、それを DLL に完全に配置できます。

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [オートメーション サーバー](../mfc/automation-servers.md)

## <a name="see-also"></a>関連項目

[Visual Studio での C/C++ Dll の作成](dlls-in-visual-cpp.md)
