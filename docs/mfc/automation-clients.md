---
title: オートメーション クライアント |Microsoft ドキュメント
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
ms.openlocfilehash: a29b11028df84a7e5e67adb7588386f77adcff06
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929040"
---
# <a name="automation-clients"></a>オートメーション クライアント
オートメーションにより別のアプリケーションで実装されているオブジェクトを操作する、または操作できるようにするオブジェクトを公開する、アプリケーションのできます。 オートメーション クライアントは、別のアプリケーションに属する公開されているオブジェクトを操作するアプリケーションです。 オブジェクトを公開するアプリケーションをオートメーション サーバーと呼びます。 クライアントは、これらのオブジェクトのプロパティおよび関数にアクセスして、サーバー アプリケーションのオブジェクトを操作します。  
  
### <a name="types-of-automation-clients"></a>オートメーション クライアントの種類  
 オートメーション クライアントの 2 つの種類があります。  
  
-   クライアントに動的に (実行時) プロパティと、サーバーの操作に関する情報を取得します。  
  
-   プロパティと、サーバーの操作を指定する静的な情報 (コンパイル時に指定) を持つクライアント。  
  
 最初の種類のクライアントが、OLE システムのクエリを実行して、サーバーのメソッドとプロパティに関する情報を取得`IDispatch`メカニズムです。 クライアントが動的に使用する適切な`IDispatch`静的クライアントは、行われる必要がありますで認識されているオブジェクトにコンパイル時に使用するは困難です。 静的には、クライアントがバインドされた、Microsoft Foundation classes を提供、 [COleDispatchDriver](../mfc/reference/coledispatchdriver-class.md)クラスです。  
  
 静的にバインドされたクライアントは、クライアント アプリケーションに静的にリンクされているプロキシ クラスを使用します。 このクラスは、サーバー アプリケーションのプロパティと操作のタイプ セーフな C++ カプセル化を提供します。  
  
 クラス`COleDispatchDriver`オートメーションのクライアント側のプリンシパルのサポートを提供します。 使用して、**新しい項目の追加**から派生するクラスを作成するダイアログ ボックスで、`COleDispatchDriver`です。  
  
 プロパティと、サーバー アプリケーションのオブジェクトの関数を記述するタイプ ライブラリ ファイルを指定します。 項目の追加 ダイアログ ボックスは、このファイルを読み取り、作成、 `COleDispatchDriver`-アプリケーションがオブジェクトにアクセスするサーバー アプリケーションの C++ では、タイプ セーフな方法で呼び出すことができるメンバー関数でのクラスを派生します。 継承した追加機能`COleDispatchDriver`の適切なオートメーション サーバーを呼び出しプロセスを簡略化します。  
  
### <a name="handling-events-in-automation-clients"></a>オートメーション クライアントにおけるイベントの処理  
 オートメーション クライアントでイベントを処理する場合は、シンク インターフェイスを追加する必要があります。 MFC は、ActiveX コントロール用のシンク インターフェイスを追加するその他の COM サーバーをサポートしていませんウィザードでサポートを提供します。 COM サーバーにより記述されたソース インターフェイス用の MFC クライアントのシンク インターフェイスを追加する方法については、文書を参照してください: MFC-Based COM クライアント (KB 181845) でシンク インターフェイスを作成するのに[ http://support.microsoft.com/default.aspxscid=kb; en-us; 181845](http://support.microsoft.com/default.aspxscid=kb;en-us;181845)です。  
  
## <a name="see-also"></a>関連項目  
 [オートメーション クライアント: タイプ ライブラリの使用](../mfc/automation-clients-using-type-libraries.md)   
 [オートメーション](../mfc/automation.md)   
 [MFC アプリケーション ウィザード](../mfc/reference/mfc-application-wizard.md)

