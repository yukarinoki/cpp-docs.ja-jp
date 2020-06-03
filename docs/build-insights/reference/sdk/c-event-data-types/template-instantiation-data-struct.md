---
title: TEMPLATE_INSTANTIATION_DATA構造
description: C++ ビルド インサイト SDK TEMPLATE_INSTANTIATION_DATA構造体のリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TEMPLATE_INSTANTIATION_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: a38d19368e7c0a9912907f1da6e7a2e31ffe8d90
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325326"
---
# <a name="template_instantiation_data-structure"></a>TEMPLATE_INSTANTIATION_DATA構造

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

この`TEMPLATE_INSTANTIATION_DATA`構造体は、テンプレートのインスタンス化を記述します。

## <a name="syntax"></a>構文

```cpp
typedef struct TEMPLATE_INSTANTIATION_DATA_TAG
{
    unsigned long long  SpecializationSymbolKey;
    unsigned long long  PrimaryTemplateSymbolKey;
    int                 KindCode;

} TEMPLATE_INSTANTIATION_DATA;
```

## <a name="members"></a>メンバー

|  |  |
|--|--|
| `SpecializationSymbolKey` | テンプレート特化の種類のキー。 この値は、分析されるトレース内で一意です。 |
| `PrimaryTemplateSymbolKey` | 特殊化された基本テンプレートの種類のキー。 この値は、分析されるトレース内で一意です。 |
| `KindCode` | テンプレートのインスタンス化の種類。 詳細については、「 [TEMPLATE_INSTANTIATION_KIND_CODE](template-instantiation-kind-code-enum.md)」を参照してください。 |

## <a name="remarks"></a>解説

構造内の`TEMPLATE_INSTANTIATION_DATA`キーは、分析されるトレース内で一意です。 ただし、異なるコンパイラのフロントエンド パスから来る 2 つの異なるキーは、2 つの同じ型を指している可能性があります。 複数の`TEMPLATE_INSTANTIATION_DATA`コンパイラ フロントエンド パスから情報を取得する場合は[、SYMBOL_NAME](../event-table.md#symbol-name)イベントを使用して、2 つの型が同じかどうかを判断します。 `SymbolName`イベントは、すべてのテンプレートのインスタンス化が行われた後、コンパイラのフロントエンド パスの最後に出力されます。

::: moniker-end
