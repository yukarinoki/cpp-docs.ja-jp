---
title: オートメーション クライアント |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- clients, Automation
- Automation clients
- type libraries, Automation clients
- clients
ms.assetid: 84e34a79-06f6-4752-a33b-ae0ede1d8ecf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c4a4327e1c3e4d65c5bdc3b822cf2cdfc1ec0353
ms.sourcegitcommit: a738519aa491a493a8f213971354356c0e6a5f3a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/05/2018
ms.locfileid: "48820595"
---
# <a name="automation-clients"></a>オートメーション クライアント

Automation により、別のアプリケーションで実装されているオブジェクトを操作する、または操作できるようにするオブジェクトを公開するアプリケーション。 オートメーション クライアントは、別のアプリケーションに属する公開されているオブジェクトを操作できるアプリケーションです。 オブジェクトを公開するアプリケーションをオートメーション サーバーと呼びます。 クライアントは、これらのオブジェクトのプロパティおよび関数にアクセスして、サーバー アプリケーションのオブジェクトを操作します。

### <a name="types-of-automation-clients"></a>オートメーション クライアントの種類

オートメーション クライアントの 2 種類あります。

- 動的に (実行時に) のクライアントは、プロパティと、サーバーの操作に関する情報を取得します。

- プロパティと、サーバーの操作を指定する静的な情報 (コンパイル時に提供) を持つクライアント。

最初の種類のクライアントは、OLE システムのクエリを実行して、サーバーのメソッドとプロパティに関する情報を取得`IDispatch`メカニズム。 クライアントが動的に使用するための適切な`IDispatch`静的クライアントの場合に認識される必要があります駆動オブジェクトがコンパイルを使用することは困難です。 静的には、クライアントがバインドされている、Microsoft Foundation classes 提供、 [COleDispatchDriver](../mfc/reference/coledispatchdriver-class.md)クラス。

静的クライアントでは、クライアント アプリケーションで静的にリンクされているプロキシ クラスを使用します。 このクラスは、サーバー アプリケーションのプロパティと操作のタイプ セーフな C++ のカプセル化を提供します。

クラスは、`COleDispatchDriver`オートメーションのクライアント側のプリンシパルのサポートを提供します。 使用して、**新しい項目の追加**から派生したクラスを作成するダイアログ ボックスで、`COleDispatchDriver`します。

プロパティと、サーバー アプリケーションのオブジェクトの関数を記述するタイプ ライブラリ ファイルを指定します。 項目の追加 ダイアログ ボックスがこのファイルを読み取り、作成、 `COleDispatchDriver`-クラス、タイプ セーフな方法で C++ では、サーバー アプリケーションのオブジェクトにアクセスするアプリケーションを呼び出すことができるメンバー関数を派生します。 追加の機能が継承`COleDispatchDriver`オートメーション サーバーを適切な呼び出しのプロセスを簡略化します。

### <a name="handling-events-in-automation-clients"></a>オートメーション クライアントにおけるイベントの処理

オートメーション クライアントでイベントを処理する場合は、シンク インターフェイスを追加する必要があります。 MFC では、他の COM サーバーをサポートしていません、ActiveX コントロール用のシンク インターフェイスを追加するウィザードのサポートを提供します。 ソース インターフェイスの COM サーバーで説明されている MFC クライアントでシンク インターフェイスを追加する方法については、文書を参照してください。: MFC-Based COM クライアント (KB 181845) でシンク インターフェイスを作成で[ http://support.microsoft.com/default.aspxscid=kb181845;](http://support.microsoft.com/default.aspxscid=kb;181845)します。

## <a name="see-also"></a>関連項目

[オートメーション クライアント: タイプ ライブラリの使用](../mfc/automation-clients-using-type-libraries.md)<br/>
[オートメーション](../mfc/automation.md)<br/>
[MFC アプリケーション ウィザード](../mfc/reference/mfc-application-wizard.md)

