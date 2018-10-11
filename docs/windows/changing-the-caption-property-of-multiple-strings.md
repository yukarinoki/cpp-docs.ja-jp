---
title: Caption プロパティの複数の文字列リソース (C++) の変更 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- String editor [C++], changing properties of multiple strings
- string tables [C++], changing caption of multiple strings
ms.assetid: 82ac4389-fd9c-4794-a18f-c6bf5b253bd7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fe08462c95750f483cdec5650fccb1c199505ee1
ms.sourcegitcommit: 3a141cf07b5411d5f1fdf6cf67c4ce928cf389c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/11/2018
ms.locfileid: "49082398"
---
# <a name="changing-the-caption-property-of-multiple-string-resources-c"></a>Caption プロパティの複数の文字列リソース (C++) の変更

次の手順では、複数の文字列の caption プロパティを変更する方法を示します。

### <a name="to-change-the-caption-property-of-multiple-strings"></a>複数の文字列の caption プロパティを変更するには

1. アイコンをダブルクリックして、文字列テーブルを開く[リソース ビュー](../windows/resource-view-window.md)します。

   > [!NOTE]
   > プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。

2. 押しながら変更する文字列を選択、 **Ctrl**キーのそれぞれをクリックするとします。

3. [プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)、変更するプロパティの新しい値を入力します。

4. **Enter** キーを押します。

マネージ プロジェクト (共通言語ランタイムを対象とするもの) にリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、次を参照してください。[チュートリアル: Windows フォームのローカリゼーション](/previous-versions/visualstudio/visual-studio-2010/y99d1cd3)します。

## <a name="requirements"></a>要件

Win32

## <a name="see-also"></a>関連項目

[ストリング エディター](../windows/string-editor.md)  