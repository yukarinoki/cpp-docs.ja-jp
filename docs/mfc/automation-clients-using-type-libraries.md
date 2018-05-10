---
title: 'オートメーション クライアント: タイプ ライブラリの使用 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- MkTypLib
dev_langs:
- C++
helpviewer_keywords:
- clients, Automation
- dispatch class [MFC]
- Automation clients, type libraries
- type libraries, Automation clients
- ODL (Object Description Language)
- ODL files
- classes [MFC], dispatch
- MkTypLib tool
- .odl files
ms.assetid: d405bc47-118d-4786-b371-920d035b2047
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 67fa0f5d164ae325caff576fb41695fc8689fda0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="automation-clients-using-type-libraries"></a>オートメーション クライアント : タイプ ライブラリの使用
オートメーション クライアントは、クライアントがサーバーのオブジェクトを操作する場合、サーバー オブジェクトのプロパティとメソッドに関する情報にすることが必要です。 プロパティがあるデータ型です。メソッドは、多くの場合、戻り値とパラメーターを受け取る。 クライアントでは、サーバー オブジェクトの型に静的にバインドするためにこれらのすべてのデータ型に関する情報が必要です。  
  
 この型情報は、いくつかの方法で既知作成できます。 推奨される方法では、タイプ ライブラリを作成します。  
  
 詳細について[MkTypLib](http://msdn.microsoft.com/library/windows/desktop/aa366797)、Windows SDK を参照してください。  
  
 Visual C がタイプ ライブラリ ファイルの読み取りおよびから派生するディスパッチ クラスを作成する[COleDispatchDriver](../mfc/reference/coledispatchdriver-class.md)です。 そのクラスのオブジェクトには、プロパティと、サーバー オブジェクトの複製操作があります。 アプリケーションがこのオブジェクトのプロパティと、操作を呼び出すし、機能を継承`COleDispatchDriver`さらに、サーバー オブジェクトにルーティングする OLE システムにこれらの呼び出しをルーティングします。  
  
 Visual C を使用するプロジェクトが作成されたときにオートメーションのサポートを選択した場合のこのタイプ ライブラリ ファイルが自動的に維持します。 .Tlb ファイルは、各ビルドの一部として、MkTypLib でビルドされます。  
  
### <a name="to-create-a-dispatch-class-from-a-type-library-tlb-file"></a>タイプ ライブラリ (.tlb) ファイルからディスパッチ クラスを作成するには  
  
1.  クラス ビューまたはソリューション エクスプ ローラーで、プロジェクトを右クリックし、をクリックして**追加**] をクリックし、**クラスの追加**ショートカット メニューの [します。  
  
2.  **クラスの追加**ダイアログ ボックスで、 **Visual C + MFC**左側のウィンドウでフォルダーです。 選択、 **TypeLib からの MFC クラス** アイコンをクリックして、右側のウィンドウを**開く**です。  
  
3.  **Typelib クラス追加ウィザード** ダイアログ ボックスからタイプ ライブラリを選択、**使用可能なタイプ ライブラリ**ドロップダウン リスト。 **インターフェイス**ボックスが選択されているタイプ ライブラリの使用可能なインターフェイスが表示されます。  
  
    > [!NOTE]
    >  インターフェイスは、1 つ以上のタイプ ライブラリから選択できます。  
  
     インターフェイスを選択して、それらをダブルクリックするかをクリックする、**追加**ボタンをクリックします。 これを行うには、ディスパッチ クラスの名前に表示されます、**生成されたクラス**ボックス。 内のクラス名を編集することができます、`Class`ボックス。  
  
     **ファイル** ボックスには、クラスの宣言されるファイルが表示されます。 (このファイル名もを編集することができます。) ヘッダーと実装情報がプロジェクト ディレクトリ以外のディレクトリまたは既存のファイルで記述する場合、その他のファイルを選択する [参照] ボタンを使用できます。  
  
    > [!NOTE]
    >  選択したインターフェイスのすべてのディスパッチ クラスは、ここで指定したファイルに格納されます。 インターフェイスを別のヘッダーで宣言する場合は、このウィザードの各ヘッダー ファイルを作成するを実行する必要があります。  
  
    > [!NOTE]
    >  いくつかのタイプ ライブラリの情報を持つファイルに格納可能性があります。DLL、です。OCX、または。OLB ファイル拡張子。  
  
4.  **[完了]** をクリックします。  
  
     ウィザードは、指定したクラスとファイル名を使用して、ディスパッチ クラスのコードが記述されます。  
  
## <a name="see-also"></a>関連項目  
 [オートメーション クライアント](../mfc/automation-clients.md)

