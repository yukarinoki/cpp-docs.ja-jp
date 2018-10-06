---
title: InitInstance メンバー関数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- InitInstance
dev_langs:
- C++
helpviewer_keywords:
- InitInstance method [MFC]
- applications [MFC], initializing
- MFC, initializing
- initializing MFC applications
ms.assetid: 4ef09267-ff7f-4c39-91a0-57454a264f83
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cafc3868d41dcf90baabbf05e0d5a4671c5b11fc
ms.sourcegitcommit: a738519aa491a493a8f213971354356c0e6a5f3a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/05/2018
ms.locfileid: "48820296"
---
# <a name="initinstance-member-function"></a>InitInstance メンバー関数

Windows オペレーティング システムは、複数のコピー、または「インスタンス」の同じアプリケーションを実行することができます。 `WinMain` 呼び出し[InitInstance](../mfc/reference/cwinapp-class.md#initinstance)たびに、アプリケーションの新しいインスタンスを開始します。

標準`InitInstance`MFC アプリケーション ウィザードによって作成された実装は、次のタスクを実行します。

- 中央のアクションとしては、ドキュメント、ビュー、およびフレーム ウィンドウを作成するドキュメント テンプレートを作成します。 このプロセスの説明は、次を参照してください。[ドキュメント テンプレートの作成](../mfc/document-template-creation.md)です。

- .Ini ファイルまたは最近使用したファイルの名前を含む、Windows レジストリから標準のファイル オプションを読み込みます。

- 1 つまたは複数のドキュメント テンプレートを登録します。

- MDI アプリケーションのメイン フレーム ウィンドウを作成します。

- コマンドラインで指定されたドキュメントを開くか、新しい空の文書を開くには、コマンド ラインを処理します。

独自の初期化コードを追加したり、ウィザードによって作成されたコードを変更することができます。

> [!NOTE]
>  MFC アプリケーションは、シングルスレッド アパートメント (STA) として初期化する必要があります。 呼び出す場合[CoInitializeEx](/windows/desktop/api/combaseapi/nf-combaseapi-coinitializeex)で、`InitInstance`オーバーライド、COINIT_APARTMENTTHREADED (COINIT_MULTITHREADED ではなく) を指定します。 詳細については、[prb] を参照してください: MFC アプリケーションとして、マルチ スレッド アパートメント (828643) でアプリケーションを初期化するときの応答を停止[ http://support.microsoft.com/default.aspxscid=kb828643;](http://support.microsoft.com/default.aspxscid=kb;828643)します。

## <a name="see-also"></a>関連項目

[CWinApp: アプリケーション クラス](../mfc/cwinapp-the-application-class.md)
