---
title: 追加または削除の文字列リソース (C++)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.string
helpviewer_keywords:
- strings [C++], adding to string tables
- string tables [C++], deleting strings
- strings [C++], deleting in string tables
- string tables [C++], adding strings
ms.assetid: 077077b4-0f4b-4633-92d6-60b321164cab
ms.openlocfilehash: 6c7614c78bb442abe7ae8c174f0bef15afb96e39
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50617933"
---
# <a name="adding-or-deleting-a-string-resource-c"></a>追加または削除の文字列リソース (C++)

使用して、文字列テーブルに新しいエントリをすばやく挿入できる、**文字列**エディター。 新しい文字列は、テーブルの末尾に配置され、[次へ] の使用可能な識別子が与えられます。 編集することができます、 **ID**、**値**、または**キャプション**プロパティで、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)に応じて。

**文字列**エディターでは、既に使用されている ID を使用しないことを確認します。 ID を既に使用して、選択した場合、**文字列**エディターは通知し、たとえば一般的な一意の ID を割り当てる`IDS_STRING58113`します。

### <a name="to-add-a-string-table-entry"></a>ストリング テーブルのエントリを追加するには

1. アイコンをダブルクリックして、文字列テーブルを開く[リソース ビュー](../windows/resource-view-window.md)します。

   > [!NOTE]
   > プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。

2. 文字列テーブル内で右クリックし、**新しい文字列**ショートカット メニューから。

3. **文字列**エディターで、 **ID**からドロップダウン リストの ID または ID で直接の場所の種類。

4. 編集、**値**、必要な場合。

5. エントリを入力、**キャプション**します。

   > [!NOTE]
   > Null 文字列は、Windows ストリング テーブルでは許可されません。 「を入力してください、文字列のこのテーブルのエントリ」を選択するメッセージが表示されます、null 文字列である文字列テーブルにエントリを作成する場合

### <a name="to-delete-a-string-table-entry"></a>文字列テーブルのエントリを削除するには

1. 削除するエントリを選択します

2. **編集** メニューのをクリックして**削除**します。

\- または -

- 削除する文字列を右クリックして**削除**ショートカット メニューから。

\- または -

- キーを押して、**削除**キー。

マネージ プロジェクト (共通言語ランタイムを対象とするもの) にリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、次を参照してください。[チュートリアル: Windows フォームのローカリゼーション](/previous-versions/visualstudio/visual-studio-2010/y99d1cd3)します。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[ストリング エディター](../windows/string-editor.md)