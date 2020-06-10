---
title: オートメーション クライアント
ms.date: 11/04/2016
helpviewer_keywords:
- clients, Automation
- Automation clients
- type libraries, Automation clients
- clients
ms.assetid: 84e34a79-06f6-4752-a33b-ae0ede1d8ecf
ms.openlocfilehash: 9c34f6fccd06635dfb686e6eb1f2cf895bb86989
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84626080"
---
# <a name="automation-clients"></a>オートメーション クライアント

オートメーションを使用すると、アプリケーションが別のアプリケーションで実装されているオブジェクトを操作したり、オブジェクトを公開して操作できるようにしたりすることができます。 オートメーションクライアントは、別のアプリケーションに属している公開されたオブジェクトを操作できるアプリケーションです。 オブジェクトを公開するアプリケーションは、オートメーションサーバーと呼ばれます。 クライアントは、これらのオブジェクトのプロパティと関数にアクセスすることによって、サーバーアプリケーションのオブジェクトを操作します。

### <a name="types-of-automation-clients"></a>オートメーションクライアントの種類

オートメーションクライアントには、次の2種類があります。

- 動的に (実行時に) クライアントは、サーバーのプロパティと操作に関する情報を取得します。

- サーバーのプロパティと操作を指定する静的な情報を (コンパイル時に提供される) クライアント。

最初の種類のクライアントは、OLE システムの機構を照会することによって、サーバーのメソッドとプロパティに関する情報を取得し `IDispatch` ます。 動的クライアントにはを使用するのが適切ですが、を使用するのは、実行 `IDispatch` 中のオブジェクトがコンパイル時に認識される必要がある静的クライアントでは使用できません。 静的にバインドされたクライアントの場合、Microsoft Foundation classes は[COleDispatchDriver](reference/coledispatchdriver-class.md)クラスを提供します。

静的バインドクライアントは、クライアントアプリケーションと静的にリンクされるプロキシクラスを使用します。 このクラスは、サーバーアプリケーションのプロパティと操作のタイプセーフな C++ カプセル化を提供します。

クラスは、 `COleDispatchDriver` オートメーションのクライアント側のプリンシパルサポートを提供します。 [**新しい項目の追加**] ダイアログボックスを使用して、から派生したクラスを作成し `COleDispatchDriver` ます。

次に、サーバーアプリケーションのオブジェクトのプロパティと関数を記述するタイプライブラリファイルを指定します。 [項目の追加] ダイアログボックスでは、このファイルが読み取られ、 `COleDispatchDriver` アプリケーションが型セーフな方法でサーバーアプリケーションのオブジェクトにアクセスするために呼び出すことができるメンバー関数と共に、派生クラスが作成されます。 から継承された追加機能によっ `COleDispatchDriver` て、適切なオートメーションサーバーの呼び出しプロセスが簡単になります。

### <a name="handling-events-in-automation-clients"></a>オートメーションクライアントでのイベントの処理

オートメーションクライアントでイベントを処理する場合は、シンクインターフェイスを追加する必要があります。 MFC では、ActiveX コントロールのシンクインターフェイスを追加するウィザードをサポートしていますが、他の COM サーバーはサポートされていません。

## <a name="see-also"></a>関連項目

[オートメーション クライアント : タイプ ライブラリの使用](automation-clients-using-type-libraries.md)<br/>
[Automation](automation.md)<br/>
[MFC アプリケーションウィザード](reference/mfc-application-wizard.md)
