---
description: '詳細情報: ドキュメントの使用'
title: ドキュメントの使い方
ms.date: 11/04/2016
helpviewer_keywords:
- documents [MFC], C++ applications
- data [MFC], reading
- documents [MFC]
- files [MFC], writing to
- data [MFC], documents
- files [MFC]
- views [MFC], C++ applications
- document/view architecture [MFC], documents
- reading data [MFC], documents and views
- printing [MFC], documents
- writing to files [MFC]
ms.assetid: f390d6d8-d0e1-4497-9b6a-435f7ce0776c
ms.openlocfilehash: 486604733808fb027d6dd0fbf81bb670c85313f8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154501"
---
# <a name="using-documents"></a>ドキュメントの使い方

共同作業、ドキュメントとビュー:

- アプリケーション固有の [データ](../mfc/managing-data-with-document-data-variables.md)を格納、管理、および表示します。

- データを操作するための [ドキュメントデータ変数](../mfc/managing-data-with-document-data-variables.md) で構成されるインターフェイスを提供します。

- ファイルの [書き込みと読み取り](../mfc/serializing-data-to-and-from-files.md)に参加します。

- [印刷](../mfc/role-of-the-view-in-printing.md)に参加します。

- アプリケーションのほとんどのコマンドとメッセージを[処理](../mfc/handling-commands-in-the-document.md)します。

このドキュメントは、特にデータの管理に関連しています。 通常は、ドキュメントクラスのメンバー変数にデータを格納します。 ビューでは、これらの変数を使用して、表示と更新のためにデータにアクセスします。 ドキュメントの既定のシリアル化機構は、ファイルとの間でのデータの読み取りと書き込みを管理します。 ドキュメントでは、コマンドを処理することもできます (ただし、WM_COMMAND 以外の Windows メッセージは処理できません)。

## <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [CDocument からのドキュメント クラスの派生](../mfc/deriving-a-document-class-from-cdocument.md)

- [ドキュメント データ変数を使ったデータ管理](../mfc/managing-data-with-document-data-variables.md)

- [データのファイルへのシリアル化](../mfc/serializing-data-to-and-from-files.md)

- [シリアル化機構のバイパス](../mfc/bypassing-the-serialization-mechanism.md)

- [ドキュメントでのコマンドの処理](../mfc/handling-commands-in-the-document.md)

- [OnNewDocument メンバー関数](../mfc/reference/cdocument-class.md#onnewdocument)

- [DeleteContents メンバー関数](../mfc/reference/cdocument-class.md#deletecontents)

## <a name="see-also"></a>関連項目

[ドキュメント/ビューアーキテクチャ](../mfc/document-view-architecture.md)
