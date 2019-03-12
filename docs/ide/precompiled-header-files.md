---
title: プリコンパイル済みヘッダー ファイル
ms.date: 11/04/2016
f1_keywords:
- stdafx.h
helpviewer_keywords:
- stdafx.h
- PCH files, file descriptions
- .pch files, file descriptions
- precompiled header files, file descriptions
- stdafx.cpp
ms.assetid: 8228d87a-5609-41f3-9697-b16094c000e5
ms.openlocfilehash: c9df203aac7d43c4c16850dd617639a85234917b
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2019
ms.locfileid: "57740880"
---
# <a name="precompiled-header-files"></a>プリコンパイル済みヘッダー ファイル

これらのファイルは、プリコンパイル済みヘッダー ファイル *Projname*.pch とプリコンパイル済み型ファイル Stdafx.obj をビルドするために使用されます。

また、これらのファイルは *Projname* ディレクトリに配置されます。 ソリューション エクスプローラーでは、Stdafx.h が Header Files フォルダーに配置され、Stdafx.cpp が Source Files フォルダーに配置されます。

|ファイル名|説明|
|---------------|-----------------|
|stdafx.h|頻繁に使用されるものの、ほとんど変更されない標準のシステム インクルード ファイルとプロジェクト固有のインクルード ファイル用のインクルード ファイル。<br /><br /> stdafx.h ではどのような _AFX_NO_XXX マクロも定義または定義解除しないでください。|
|stdafx.cpp|プリプロセッサ ディレクティブ `#include "stdafx.h"` が含まれており、プリコンパイル済み型用のインクルード ファイルが追加されています。 ヘッダー ファイルなどの任意の型のプリコンパイル済みファイルは、コンパイルが必要なファイルだけにコンパイルを制限することで、コンパイル時間の短縮を支援します。 初めてプロジェクトをビルドすると、プリコンパイル済みヘッダー ファイルが存在することによって、その後のビルドは非常に速くなることに気付くでしょう。|

## <a name="see-also"></a>関連項目

[Visual C++ プロジェクトに対して作成されるファイルの種類](../ide/file-types-created-for-visual-cpp-projects.md)<br>
[プロジェクトのプロパティの操作](../ide/working-with-project-properties.md)
