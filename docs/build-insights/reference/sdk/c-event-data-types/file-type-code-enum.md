---
title: FILE_TYPE_CODE 列挙型
description: C++ Build Insights SDK の FILE_TYPE_CODE 列挙型のリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FILE_TYPE_CODE
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: ddd625829e94786c0daddf0e78b914e225b2ecfb
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92921024"
---
# <a name="file_type_code-enum"></a>FILE_TYPE_CODE 列挙型

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`FILE_TYPE_CODE` 列挙型によって、ファイルの種類を記述します。

## <a name="members"></a>メンバー

| 名前 | 値 | 説明 |
|--|--|--|
| `FILE_TYPE_CODE_OTHER` | 0 (0x00000000) | この列挙型に含まれていないファイルの種類。 |
| `FILE_TYPE_CODE_OBJ` | 1 (0x00000001) | オブジェクト (\*.obj) ファイル。 |
| `FILE_TYPE_CODE_EXECUTABLE_IMAGE` | 2 (0x00000002) | 実行可能ファイル (\*.exe) または DLL (\*.dll) ファイル。 |
| `FILE_TYPE_CODE_LIB` | 3 (0x00000003) | スタティック ライブラリ (*.lib) ファイル。 |
| `FILE_TYPE_CODE_IMP_LIB` | 4 (0x00000004) | インポート ライブラリ (*.lib) |
| `FILE_TYPE_CODE_EXP` | 5 (0x00000005) | エクスポート (*.exp) ファイル。 |

## <a name="remarks"></a>注釈

::: moniker-end
