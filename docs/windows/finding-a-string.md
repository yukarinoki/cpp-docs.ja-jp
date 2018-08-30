---
title: 文字列の検索 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.string
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], searching
- strings [C++]
ms.assetid: c2497173-f356-4f77-97d6-f0ac41782510
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3e04caa4aa927bd24bc1a5cd86f5d390e1c376b7
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43197536"
---
# <a name="finding-a-string"></a>文字列の検索

文字列テーブル内 1 つまたは複数の文字列を検索して使用することができます[正規](/visualstudio/ide/using-regular-expressions-in-visual-studio)で、**ファイル内の検索**コマンド (**編集**メニュー) 文字列のすべてのインスタンスを検索するにはパターンに一致します。

### <a name="to-find-a-string-in-the-string-table"></a>文字列テーブルに文字列を検索するには

1. アイコンをダブルクリックして、文字列テーブルを開く[リソース ビュー](../windows/resource-view-window.md)します。

   > [!NOTE]
   > プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。

2. **編集** メニューのをクリックして**検索し、置換**を選択し、**検索**します。

3. **検索**ボックス、ドロップダウン リストから、以前の検索文字列を選択または検索する文字列のキャプション テキストまたはリソース識別子を入力します。

4. いずれかの選択、**検索**オプション。

5. クリックして**次を検索**します。

   > [!TIP]
   > ファイルを検索するときに正規表現を使用する、**ファイル内の検索**コマンド。 正規表現パターンに一致かの右側にボタンをクリックする、**検索**検索の正規表現の一覧を表示するボックスです。 この一覧から式を選択すると、検索文字列として設定されます、**検索**ボックス。 正規表現を使用する場合は必ず、**使用: 正規表現** チェック ボックスをオンします。

マネージ プロジェクト (共通言語ランタイムを対象とするもの) にリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、次を参照してください。[チュートリアル: Windows フォームのローカリゼーション](/previous-versions/visualstudio/visual-studio-2010/y99d1cd3\(v=vs.100\))します。

## <a name="requirements"></a>要件

Win32

## <a name="see-also"></a>関連項目

[ストリング エディター](../windows/string-editor.md)  