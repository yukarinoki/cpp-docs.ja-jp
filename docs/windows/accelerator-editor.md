---
title: アクセラレータ エディター (C++)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.accelerator.F1
helpviewer_keywords:
- accelerator tables [C++], editing
- tables [C++], accelerator key
- accelerator keys [C++]
- resource editors [C++], Accelerator editor
- keyboard shortcuts [C++], Accelerator editor
ms.assetid: 013c30b6-5d61-4f1c-acef-8bd15bed7060
ms.openlocfilehash: fdb2d9cf0954142da990a0a9f995cb482060345d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50621495"
---
# <a name="accelerator-editor-c"></a>アクセラレータ エディター (C++)

アクセラレータ テーブルは、アクセラレータ キー (ショートカット キーとも呼ばれます) の一覧を含む C++ Windows リソースとそれらに関連付けられたコマンド識別子です。 プログラムは複数のアクセラレータ テーブルを持つことができます。

通常、アクセラレータはメニューやツール バーでも使用できるプログラム コマンドのキーボード ショートカットとして使用されます。 しかし、アクセラレータ テーブルを使用すると、関連付けられているユーザー インターフェイス オブジェクトのないコマンドにキーの組み合わせを定義できます。

[クラス ビュー](/visualstudio/ide/viewing-the-structure-of-code) を使用して、コードにアクセス キーのコマンドをフックできます。

**アクセラレータ**エディターができます。

- [アクセラレータ プロパティの設定](../windows/setting-accelerator-properties.md)

- [アクセス キーとメニュー項目との関連付け](../windows/associating-an-accelerator-key-with-a-menu-item.md)

- [アクセラレータ テーブルの編集](../windows/editing-accelerator-tables.md)

- [定義済みのアクセス キーの使用](../windows/predefined-accelerator-keys.md)

   > [!TIP]
   > 使用しているときに、**アクセラレータ**エディター、頻繁に使用されるコマンドのショートカット メニューを表示する右クリックできます。 使用できるコマンドは、ポインターの位置によって異なります。

   > [!NOTE]
   > Windows では、空のアクセラレータ テーブルは作成できません。 エントリがないアクセラレータ テーブルを作成すると、テーブルを保存する際に自動的に削除されます。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[リソース エディター](../windows/resource-editors.md)