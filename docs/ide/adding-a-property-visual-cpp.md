---
title: プロパティの追加 (Visual C++)
ms.date: 11/04/2016
helpviewer_keywords:
- interfaces, adding properties
- properties [C++], adding to interfaces
ms.assetid: 37bd4db7-efd3-4faa-87ad-64902ed16a36
ms.openlocfilehash: 3c47a5b50442f47e6042ea1232590dbdde7299ec
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50563086"
---
# <a name="adding-a-property-visual-c"></a>プロパティの追加 (Visual C++)

[プロパティ追加ウィザード](../ide/names-add-property-wizard.md)を使用して、プロジェクトのインターフェイスにメソッドを追加することができます。

### <a name="to-add-a-property-to-your-object"></a>オブジェクトにプロパティを追加するには

1. [クラス ビュー](/visualstudio/ide/viewing-the-structure-of-code)で、プロパティを追加するインターフェイスを右クリックします。

   > [!NOTE]
   > プロジェクトに属性が設定されていない限り、ライブラリ ノード内で入れ子にされるディスパッチ インターフェイスに、プロパティを追加することもできます。

1. ショートカット メニューから、**[追加]**、**[プロパティの追加]** の順にクリックします。

1. [プロパティ追加ウィザード](../ide/names-add-property-wizard.md)で、情報を指定してプロパティを作成します。

1. ウィザードの [[IDL 属性]](../ide/idl-attributes-add-property-wizard.md) ページで、プロパティのインターフェイス定義言語 (IDL) 設定を指定します。

1. **[完了]** をクリックしてプロパティを追加します。

プロパティの **Get** メソッドと `Put` メソッドは、定義されているインターフェイスの下のクラス ビューに 2 つのアイコンとして表示されます。 いずれかのアイコンをダブルクリックして、.idl ファイルのプロパティ宣言を表示できます。

- ATL インターフェイスについては、**Get** 関数と **Put** 関数が .cpp ファイルに追加され、これらの関数への参照が .h ファイルに追加されます。

- MFC ディスパッチ インターフェイスについては、実装型として**メンバー変数**を選択した場合、メソッドと変数が実装するクラスに追加されます。 実装型として **Get/Set メソッド**を選択した場合、2 つのメソッドが実装するクラスに追加されます。

## <a name="see-also"></a>参照

[COM インターフェイスの作成](../ide/creating-a-com-interface-visual-cpp.md)<br>
[COM インターフェイスの編集](../ide/editing-a-com-interface.md)<br>
[コンポーネント オブジェクト モデル](/windows/desktop/com/the-component-object-model)<br>
[インターフェイス ポインターとインターフェイス](/windows/desktop/com/interface-pointers-and-interfaces)