---
description: '詳細情報: 引用符で囲まれたファイル名を含む'
title: 引用符で囲まれたファイル名を含む
ms.date: 11/04/2016
ms.assetid: 789a047e-ea38-4c99-b71d-a2ad9c81daee
ms.openlocfilehash: b07d8dc04106a330644c30bffd1e8f36fc81fb6d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97137632"
---
# <a name="including-quoted-filenames"></a>引用符で囲まれたファイル名を含む

**ANSI 3.8.2** インクルード可能なソース ファイルの引用された名前のサポート

2 組の二重引用符 (" ") 間にインクルード ファイルのあいまいでない完全なパスを指定すると、プリプロセッサはそのパスのみを検索し、標準ディレクトリを無視します。

[#include](../preprocessor/hash-include-directive-c-cpp.md) "path-spec" に指定されたインクルード ファイルでは、ディレクトリの検索は親ファイルのディレクトリから始まり、その後にすべての祖父母ファイルのディレクトリが検索されます。 したがって、検索は現在処理中のソース ファイルが含まれるディレクトリに対して相対的に開始されます。 親の親ファイルが存在せず、見つからなかった場合は、ファイル名が山かっこで囲まれているものとして検索が続行されます。

## <a name="see-also"></a>関連項目

[プリプロセス ディレクティブ](../c-language/preprocessing-directives.md)
