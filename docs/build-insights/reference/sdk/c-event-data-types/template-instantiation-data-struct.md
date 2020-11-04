---
title: TEMPLATE_INSTANTIATION_DATA 構造体
description: C++ Build Insights SDK の TEMPLATE_INSTANTIATION_DATA 構造体のリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TEMPLATE_INSTANTIATION_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c92fbd8ee7e1fff702757d003ab3bbe0bdabd886
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923436"
---
# <a name="template_instantiation_data-structure"></a>TEMPLATE_INSTANTIATION_DATA 構造体

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`TEMPLATE_INSTANTIATION_DATA` 構造体はテンプレートのインスタンス化を表します。

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

| 名前 | [説明] |
|--|--|
| `SpecializationSymbolKey` | テンプレート特殊化の種類を表すキー。 この値は分析対象のトレース内で一意です。 |
| `PrimaryTemplateSymbolKey` | 特殊化されたプライマリ テンプレートの種類を表すキー。 この値は分析対象のトレース内で一意です。 |
| `KindCode` | テンプレート インスタンス化の種類。 詳細については、[TEMPLATE_INSTANTIATION_KIND_CODE](template-instantiation-kind-code-enum.md) に関するページを参照してください。 |

## <a name="remarks"></a>注釈

`TEMPLATE_INSTANTIATION_DATA` 構造体内のキーは分析対象のトレース内で一意です。 ただし、異なるコンパイラ フロントエンド パスから受け取る 2 つの異なるキーで、2 つの同じ型が示されている場合があります。 複数のコンパイラ フロントエンド パスからの `TEMPLATE_INSTANTIATION_DATA` 情報を使用するとき、[SYMBOL_NAME](../event-table.md#symbol-name) イベントを使用し、2 つの型が同じかどうかを判断します。 `SymbolName` イベントは、すべてのテンプレートのインスタンス化が行われた後で、コンパイラ フロントエンド パスの最後に生成されます。

::: moniker-end
