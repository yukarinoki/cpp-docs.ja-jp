---
title: 別の (c++) の 1 つのリソース ファイルから文字列の移動
ms.date: 11/04/2016
helpviewer_keywords:
- strings [C++], moving between files
- resource script files [C++], moving strings
- string editing, moving strings between resources
- String editor [C++], moving strings between files
ms.assetid: 94f8ee81-9b4c-4788-ba95-68c58db38029
ms.openlocfilehash: e89a0d44dc824c72710f8a047a18771ba8da492b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50649814"
---
# <a name="moving-a-string-from-one-resource-file-to-another-c"></a>別の (c++) の 1 つのリソース ファイルから文字列の移動

### <a name="to-move-a-string-from-one-resource-script-file-to-another"></a>文字列を別の 1 つのリソース スクリプト ファイルに移動するには

1. 両方の .rc ファイルでは、文字列テーブルを開きます。 (詳細については、次を参照してください[を表示するリソースで、リソース スクリプト ファイル プロジェクトの外側に](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)。)。

   > [!NOTE]
   > プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。

2. を選択する文字列を右クリックして**切り取り**ショートカット メニューから。

3. ターゲットにカーソルを置き**文字列エディター**ウィンドウ。

4. 文字列を移動する .rc ファイルを右クリックし、選択**貼り付け**ショートカット メニューから。

   > [!NOTE]
   > 場合、 **ID**または**値**既存の文字列の移動の競合の**ID**または**値**変換先のファイルか、 **ID**または**値**の移動先の文字列を変更します。 同じ文字列が存在する場合は**ID**、 **ID**の移動先の文字列の変更。 同じ文字列が存在する場合は**値**、**値**の移動先の文字列の変更。

マネージ プロジェクト (共通言語ランタイムを対象とするもの) にリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、次を参照してください。[チュートリアル: Windows フォームのローカリゼーション](/previous-versions/visualstudio/visual-studio-2010/y99d1cd3)します。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[ストリング エディター](../windows/string-editor.md)<br/>
[リソース ファイル](../windows/resource-files-visual-studio.md)<br/>
[ウィンドウ レイアウトをカスタマイズする](/visualstudio/ide/customizing-window-layouts-in-visual-studio)