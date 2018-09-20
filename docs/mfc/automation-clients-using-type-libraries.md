---
title: 'オートメーション クライアント: タイプ ライブラリの使用 |Microsoft Docs'
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
ms.openlocfilehash: 421040024e5dd95fb39bdc78cd54f3f7dc49bf83
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46377715"
---
# <a name="automation-clients-using-type-libraries"></a>オートメーション クライアント : タイプ ライブラリの使用

オートメーション クライアントは、クライアントがサーバーのオブジェクトを操作する場合、サーバー オブジェクトのプロパティとメソッドについての情報にすることが必要です。 プロパティがあるデータ型。メソッドは、多くの場合、戻り値とパラメーターをそのまま使用します。 クライアントでは、サーバー オブジェクトの型に静的にバインドするためにこれらすべてのデータ型に関する情報が必要です。

この型情報は、いくつかの方法で既知作成できます。 タイプ ライブラリを作成することをお勧めします。

について[MkTypLib](/windows/desktop/Midl/differences-between-midl-and-mktyplib)、Windows SDK を参照してください。

Visual C がタイプ ライブラリ ファイルの読み取りし、ディスパッチ クラスから派生した作成[COleDispatchDriver](../mfc/reference/coledispatchdriver-class.md)します。 そのクラスのオブジェクトには、プロパティと動作のサーバー オブジェクトの複製があります。 アプリケーションがこのオブジェクトのプロパティと操作を呼び出すし、機能が継承`COleDispatchDriver`順番に、サーバー オブジェクトにルーティングする OLE システムにこれらの呼び出しをルーティングします。

Visual C を使用するプロジェクトの作成時にオートメーションのサポートを選択した場合のこのタイプ ライブラリ ファイルが自動的に維持します。 MkTypLib で各ビルドの一環として、.tlb ファイルがビルドされます。

### <a name="to-create-a-dispatch-class-from-a-type-library-tlb-file"></a>タイプ ライブラリ (.tlb) ファイルからディスパッチ クラスを作成するには

1. クラス ビューまたはソリューション エクスプ ローラーでプロジェクトを右クリックし、をクリックして**追加**し**クラスの追加**ショートカット メニューの します。

1. **クラスの追加**ダイアログ ボックスで、 **Visual C/cli MFC**左側のウィンドウでフォルダー。 選択、 **TypeLib からの MFC クラス**アイコンから、右側のウィンドウとクリック**オープン**します。

1. **Typelib クラス追加ウィザード** ダイアログ ボックスで、タイプ ライブラリからの選択、**使用可能なタイプ ライブラリ**ドロップダウン リスト。 **インターフェイス**ボックスが選択されているタイプ ライブラリの使用可能なインターフェイスが表示されます。

    > [!NOTE]
    >  インターフェイスは、1 つ以上のタイプ ライブラリから選択できます。

     インターフェイスを選択して、ダブルクリックして、またはをクリックして、**追加**ボタンをクリックします。 これを行うには、ディスパッチ クラスの名前に表示されます、**生成済みクラス**ボックス。 内のクラス名を編集することができます、`Class`ボックス。

     **ファイル**ボックスには、クラスの宣言されるファイルが表示されます。 (もこのファイル名を編集することができます。) 既存のファイルまたはプロジェクト ディレクトリ以外のディレクトリに書き込まれたヘッダーと実装の情報を設定したい場合は、他のファイルを選択する、参照ボタンを使用することもできます。

    > [!NOTE]
    >  選択したインターフェイスのすべてのディスパッチ クラスは、ここで指定したファイルに格納されます。 別のヘッダーで宣言するインターフェイスを実行する場合に、各ヘッダー ファイルを作成するには、このウィザードを実行する必要があります。

    > [!NOTE]
    >  いくつかのタイプ ライブラリ情報は、ファイルに格納可能性があります。DLL、です。OCX、または。OLB ファイル拡張子。

1. **[完了]** をクリックします。

     ウィザードは、次に指定されたクラスとファイル名を使用して、ディスパッチ クラスのコードが記述されます。

## <a name="see-also"></a>関連項目

[オートメーション クライアント](../mfc/automation-clients.md)

