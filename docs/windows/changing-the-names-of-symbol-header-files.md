---
title: シンボル ヘッダー ファイル名の変更
ms.date: 11/04/2016
f1_keywords:
- vc.editors.symbol.changing.header
helpviewer_keywords:
- resource files [C++], multiple
- Resource Includes dialog box [C++]
- symbol header files [C++], changing names
- symbols [C++], symbol header files
- Resource.h
ms.assetid: b948284a-7899-402e-ab12-9f2c8480ca9d
ms.openlocfilehash: 4d9aa350d0f680e975c68bf46ac066072df044cb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50432335"
---
# <a name="changing-the-names-of-symbol-header-files"></a>シンボル ヘッダー ファイル名の変更

通常、すべてのシンボルが定義に保存`Resource.h`します。 ただし、同じディレクトリ内の複数のリソース ファイルを使用する場合などに、このインクルード ファイル名の変更が必要になることがあります。

### <a name="to-change-the-name-of-the-resource-symbol-header-file"></a>リソースのシンボル用のヘッダー ファイルの名前を変更するには

1. [リソース ビュー](../windows/resource-view-window.md)を .rc ファイルを右クリックして[リソース ファイルのインクルード](../windows/resource-includes-dialog-box.md)ショートカット メニューから。

   > [!NOTE]
   > プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。

2. **シンボル ヘッダー ファイル**ボックスに、インクルード ファイルの新しい名前を入力します。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[リソース シンボルの表示](../windows/viewing-resource-symbols.md)<br/>
[定義済みシンボル ID](../windows/predefined-symbol-ids.md)