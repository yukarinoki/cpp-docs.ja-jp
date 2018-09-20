---
title: 'シンボル: リソース識別子 (C++) |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.symbol.identifiers
dev_langs:
- C++
helpviewer_keywords:
- symbols [C++], resource identifiers
- symbols [C++], creating
- resource symbols
- symbols [C++], editing
- resource editors [C++], resource symbols
ms.assetid: 8fccc09a-0237-4a65-b9c4-57d60c59e324
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c3bbcc774115311cd4ed0f302e4d9812ecfc6505
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46422264"
---
# <a name="symbols-resource-identifiers-c"></a>シンボル: リソース識別子 (C++)

シンボルは、2 つの部分で構成されるリソース識別子 (ID) です。1 つはテキスト文字列 (シンボル名) で、整数値 (シンボル値) にマップされます。 例えば:

```
IDC_EDITNAME = 5100
```

シンボル名は一般的に、識別子と呼ばれます。

シンボルは、ソース コード内で、およびリソース エディターで作業している間に、リソースおよびユーザー インターフェース オブジェクトを参照するためのわかりやすい手段を提供します。 シンボルは [[リソース シンボル] ダイアログ ボックス](../windows/viewing-resource-symbols.md)を使用して、都合の良い 1 箇所に表示して操作することができます。

新しいリソースやリソース オブジェクトを作成する際、 [リソース エディター](../windows/resource-editors.md) は、リソースの既定の名前 (たとえば `IDC_RADIO1`) を提供し、値をそれに割り当てます。 名前と値の定義が Resource.h ファイルに格納されます。

> [!NOTE]
> リソースやリソース オブジェクトを 1 つの .rc ファイルから別のファイルにコピーする際、Visual C++ は、転送されるリソースのシンボル値、またはシンボル名と値を変更する可能性があります。これは、既存のファイルのシンボル名や値との競合を回避するためです。

アプリケーションのサイズが大きくなり、複雑になるにつれ、リソースとシンボルの数も増えます。 いくつかのファイルに散在する大量のシンボルを追跡することは困難な場合があります。 [[リソース シンボル] ダイアログ ボックス](../windows/resource-symbols-dialog-box.md) を使用すると、シンボルを簡単に管理することができます。これは集中ツールであり、以下を行えます。

- [リソース シンボルの表示](../windows/viewing-resource-symbols.md)

- [新しいシンボルの作成](../windows/creating-new-symbols.md)

- [未割り当てシンボルの変更](../windows/changing-unassigned-symbols.md)

- [未割り当てシンボルの削除](../windows/deleting-unassigned-symbols.md)

- [特定のシンボルに対するリソース エディターのオープン](../windows/opening-the-resource-editor-for-a-given-symbol.md)

- [シンボルまたはシンボル名 (ID) の変更](../windows/changing-a-symbol-or-symbol-name-id.md)

- [シンボルの数値の変更](../windows/changing-a-symbol-s-numeric-value.md)

- [シンボル ヘッダー ファイル名の変更](../windows/changing-the-names-of-symbol-header-files.md)

- [共有シンボル (読み取り専用) または計算型シンボルのインクルード](../windows/including-shared-read-only-or-calculated-symbols.md)

- [定義済みシンボル ID の表示](../windows/predefined-symbol-ids.md)

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>要件

Win32

## <a name="see-also"></a>関連項目

[方法: リソース内のシンボルを検索する](../windows/how-to-search-for-symbols-in-resources.md)<br/>
[リソース エディター](../windows/resource-editors.md)<br/>
[リソース ファイル](../windows/resource-files-visual-studio.md)