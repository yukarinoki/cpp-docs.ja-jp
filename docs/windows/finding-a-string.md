---
title: 検索文字列リソース (C++) |Microsoft Docs
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
ms.openlocfilehash: 1e331401a3a2a789b13bc21b76c9b1cbfcb30e33
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2018
ms.locfileid: "44318501"
---
# <a name="finding-a-string-resource-c"></a>検索文字列リソース (C++)

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