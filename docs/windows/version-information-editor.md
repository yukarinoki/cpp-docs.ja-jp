---
title: バージョン情報エディター (C++)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.version.F1
helpviewer_keywords:
- Version Information editor [C++], about Version Information editor
- editors, Version Information
- resource editors [C++], Version Information editor
ms.assetid: 772e6f19-f765-4cec-9521-0ad3eeb99f9b
ms.openlocfilehash: 817092af316fbc39b696e1ed19e1c67f9a799bd7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50667494"
---
# <a name="version-information-editor-c"></a>バージョン情報エディター (C++)

バージョン情報は、製造元および製品の識別情報、製品のリリース番号、著作権と商標の通知で構成されます。 **バージョン情報**エディターを作成および管理するこのデータは、バージョン情報リソースに格納されます。 バージョン情報リソースはアプリケーションに必須ではありませんが、アプリケーションの識別情報を収集するのに便利な場所です。 バージョン情報はセットアップ API でも使用されます。

バージョン情報リソースには、1 つの上位ブロックと 1 つ以上の下位ブロックがあります。つまり、固定された情報ブロックが上部に 1 つと、バージョン情報ブロックが下部に 1 つ以上 (他の言語や文字セット用) あります。 上部のブロックには、編集可能な数字のボックスと選択可能なドロップダウン リストの両方があります。 下位ブロックには、編集可能なテキスト ボックスだけがあります。

> [!NOTE]
> Windows 標準では、VS_VERSION_INFO という名前のバージョン リソースが 1 つだけあります。

**バージョン情報**エディターでは、することができます。

- [バージョン情報リソースの文字列の編集](../windows/editing-a-string-in-a-version-information-resource.md)

- [別の言語のバージョン情報 (新しいバージョン情報ブロック) の追加](../windows/adding-version-information-for-another-language.md)

- [バージョン情報ブロックの削除](../windows/deleting-a-version-information-block.md)

- [プログラムからのバージョン情報へのアクセス](../windows/accessing-version-information-from-within-your-program.md)

   > [!NOTE]
   > 使用しているときに、**バージョン情報**エディターの多数のインスタンスを右クリックすることで、リソース固有のコマンドのショートカット メニューを表示します。 たとえば、ブロックのヘッダー エントリを指すときにクリックすると、ショートカット メニューが表示、**新しいバージョン情報ブロック**と**バージョン情報ブロックの削除**コマンド。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[リソース エディター](../windows/resource-editors.md)<br/>
[メニューとその他のリソース](https://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)