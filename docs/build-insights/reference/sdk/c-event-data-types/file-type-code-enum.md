---
title: 列挙FILE_TYPE_CODE
description: C++ ビルド インサイト SDK FILE_TYPE_CODE列挙型参照。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FILE_TYPE_CODE
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: dea603a072d7b2f472112a75b2e9ccded78399a9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325560"
---
# <a name="file_type_code-enum"></a>列挙FILE_TYPE_CODE

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

列挙`FILE_TYPE_CODE`型は、ファイルの種類を示します。

## <a name="members"></a>メンバー

| 名前 | [値] | 説明 |
|--|--|--|
| `FILE_TYPE_CODE_OTHER` | 0 (0x0000000) | この列挙型に一覧表示されていないファイルの種類。 |
| `FILE_TYPE_CODE_OBJ` | 1 (0x00000001) | オブジェクト (\*.obj) ファイル。 |
| `FILE_TYPE_CODE_EXECUTABLE_IMAGE` | 2 (0x0000002) | 実行可能ファイル\*( .exe)\*または DLL ( .dll) ファイル。 |
| `FILE_TYPE_CODE_LIB` | 3 (0x0000003) | 静的ライブラリ (*.lib) ファイル。 |
| `FILE_TYPE_CODE_IMP_LIB` | 4 (0x0000004) | インポート ライブラリ (*.lib) |
| `FILE_TYPE_CODE_EXP` | 5 (0x0000005) | エクスポート (*.exp) ファイル。 |

## <a name="remarks"></a>解説

::: moniker-end
