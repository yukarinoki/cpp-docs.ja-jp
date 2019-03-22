---
title: バージョン情報エディター (C++)
ms.date: 02/14/2019
f1_keywords:
- vc.editors.version.F1
- vc.editors.version
helpviewer_keywords:
- Version Information editor [C++], about Version Information editor
- editors, Version Information
- resource editors [C++], Version Information editor
- version information resources [C++]
- resources [C++], editing version information
- languages, version information
- New Version Info Block
- blocks, adding
- resources [C++], adding version information
- version information, adding for languages
- blocks, deleting
- version information, deleting blocks
- resources [C++], deleting version information
- VerQueryValue
- version information, accessing from within programs
- GetFileVersionInfo
- version information
ms.assetid: 772e6f19-f765-4cec-9521-0ad3eeb99f9b
ms.openlocfilehash: 7cfb2b5426a65298c01c61541020a0f30b673f9c
ms.sourcegitcommit: c1f646c8b72f330fa8cf5ddb0f8f261ba10d16f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2019
ms.locfileid: "58328819"
---
# <a name="version-information-editor-c"></a>バージョン情報エディター (C++)

バージョン情報は、製造元および製品の識別情報、製品のリリース番号、著作権と商標の通知で構成されます。 **バージョン情報エディター**、作成して、バージョン情報リソースに格納されている、このデータを保持します。 バージョン情報リソースは、アプリケーションによっては必要ありませんが、アプリケーションを識別する情報を収集するために役立ちます。 バージョン情報はセットアップ API でも使用されます。

> [!NOTE]
> Windows 標準では、VS_VERSION_INFO という名前のバージョン リソースが 1 つだけあります。

バージョン情報リソースには、1 つの上位ブロックと 1 つ以上の下位ブロックがあります。つまり、固定された情報ブロックが上部に 1 つと、バージョン情報ブロックが下部に 1 つ以上 (他の言語や文字セット用) あります。 上部のブロックには、編集可能な数字のボックスと選択可能なドロップダウン リストの両方があります。 下位ブロックには、編集可能なテキスト ボックスだけがあります。

> [!NOTE]
> 使用しているときに、**バージョン情報エディター**、多くの場合、リソース固有のコマンドのショートカット メニューを表示する右クリックすることができます。 たとえば、ブロックのヘッダー エントリを指すときに選択すると、ショートカット メニューが表示、**新しいバージョン情報ブロック**と**バージョン情報ブロックの削除**コマンド。

## <a name="how-to"></a>方法

**バージョン情報エディター**できます。

### <a name="to-edit-a-string-in-a-version-information-resource"></a>バージョン情報リソースの文字列を編集するには

を選択して、もう一度編集を開始するには、項目を 1 回を選択します。 直接変更を加える、**バージョン情報**テーブルまたは、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)します。 加えた変更は、両方の場所で反映されます。

編集するときに、`FILEFLAGS`キー、**バージョン情報エディター**、設定することはできませんに注意してください、**デバッグ**、**プライベート ビルド**、または**特殊ビルド**プロパティで、**プロパティ**.rc ファイル ウィンドウ。

   - **バージョン情報エディター**設定、**デバッグ**プロパティを`#ifdef`、リソース スクリプトに基づく、`_DEBUG`ビルド フラグ。

  - 場合、`Private Build`キーには、**値**で設定、**バージョン情報**テーブルを対応する**プライベート ビルド**プロパティ、**プロパティ**のウィンドウ、`FILEFLAGS`鍵となる**True**します。 場合**値**はプロパティが空である**False**します。 同様に、**特殊ビルド**キー、**バージョン情報**に関連付けられているテーブル、**特殊ビルド**プロパティを`FILEFLAGS`キー。

いずれかを選択して、文字列ブロックの情報シーケンスを並べ替えることができます、**キー**または**値**列見出し。 これらの見出しは、選択した順序に情報を自動的に再配置します。

### <a name="to-add-version-information-for-another-language-new-version-info-block"></a>(新しいバージョン情報ブロック) の別の言語のバージョン情報を追加するには

1. [[リソース ビュー]](how-to-create-a-resource-script-file.md#create-resources)でバージョン情報リソースをダブルクリックして開きます。

1. バージョン情報テーブル内で右クリックし、**バージョン情報ブロックの新しい**します。

   このコマンドを使用して、現在のバージョン情報リソースにさらに情報ブロックを追加し、それに対応するプロパティを [[プロパティ] ウィンドウ](/visualstudio/ide/reference/properties-window)で開きます。

1. **[プロパティ]** ウィンドウで、新しいブロック用の適切な言語と文字セットを選びます。

### <a name="to-delete-a-version-information-block"></a>バージョン情報ブロックを削除するには

1. [[リソース ビュー]](how-to-create-a-resource-script-file.md#create-resources)でバージョン情報リソースのアイコンをダブルクリックして開きます。

1. 削除するブロック ヘッダーを右クリックして**バージョン情報ブロックの削除**します。

   このコマンドは、選択したヘッダーを削除し、他のバージョン情報をそのまま残されます。 アクションを元に戻すことはできません。

### <a name="to-access-version-information-from-within-your-program"></a>プログラム内からバージョン情報にアクセスするには

プログラム内からバージョン情報にアクセスする場合は、 [GetFileVersionInfo](/windows/desktop/api/winver/nf-winver-getfileversioninfoa) 関数と [VerQueryValue](/windows/desktop/api/winver/nf-winver-verqueryvaluea) 関数を使用します。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[リソース エディター](../windows/resource-editors.md)<br/>
<!--
[Menus and Other Resources](https://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)<br/>
[Version Information (Windows)](https://msdn.microsoft.com/library/windows/desktop/ms646981.aspx)-->
