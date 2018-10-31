---
title: 文字列リソース (C++) のプロパティの変更 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- resource identifiers, string properties
- string tables [C++], changing strings
- strings [C++], properties
ms.assetid: 0a220434-f444-4405-9a64-d28d6b965687
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a873776db6381a78b99e0323e669235b7863ea04
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50067645"
---
# <a name="changing-the-properties-of-a-string-resource-c"></a>文字列リソース (C++) のプロパティを変更します。

### <a name="to-change-a-string-or-its-identifier"></a>文字列または識別子を変更するには

1. アイコンをダブルクリックして、文字列テーブルを開く[リソース ビュー](../windows/resource-view-window.md)します。

   > [!NOTE]
   > プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。

2. 編集するをダブルクリックする文字列を選択、 **ID**、**値**、または**キャプション**列。 これで次のようなことができます。

   - 選択、 **ID**から、 **ID ドロップダウン**リスト、または型、`ID`は直接します。

   - 別の番号を入力、**値**列。

   - 入力時に編集、**キャプション**列。

        > [!NOTE]
        >  文字列のプロパティを編集することも、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)します。

マネージ プロジェクト (共通言語ランタイムを対象とするもの) にリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、次を参照してください。[チュートリアル: Windows フォームのローカリゼーション](/previous-versions/visualstudio/visual-studio-2010/y99d1cd3)します。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[ストリング エディター](../windows/string-editor.md)