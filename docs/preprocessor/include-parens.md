---
description: '詳細情報: include () import 属性'
title: include () インポート属性
ms.date: 08/29/2019
f1_keywords:
- include()
helpviewer_keywords:
- include() attribute
ms.assetid: 86c9dcb2-d9e0-4fd5-97d7-0bb3e23d6ecc
ms.openlocfilehash: e1164526f95bf1b916cd684a892fbef35027f984
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97236478"
---
# <a name="include-import-attribute"></a>include () インポート属性

**C++ 固有の仕様**

自動除外を無効にします。

## <a name="syntax"></a>構文

> **#import** *タイプライブラリ***インクルード ("**_Name1_**"** [__, "__*Name2*__"__ ...])__)__

### <a name="parameters"></a>パラメーター

*Name1*\
強制的に含まれる最初の項目。

*Name2*\
強制的に含める 2 番目の項目 (必要な場合)。

## <a name="remarks"></a>解説

タイプ ライブラリは、システム ヘッダーまたはその他のタイプ ライブラリで定義された項目の定義を含むことがあります。 `#import` は、そのような項目を自動的に除外して多重定義エラーを回避します。 一部の項目が自動的に除外されない場合は、 [コンパイラの警告 (レベル 3) C4192](../error-messages/compiler-warnings/compiler-warning-level-3-c4192.md)が表示されることがあります。 この属性を使用して、自動除外を無効にすることができます。 この属性は、含まれるタイプライブラリ項目の名前ごとに1つずつ、任意の数の引数を受け取ることができます。

**END C++ 固有の仕様**

## <a name="see-also"></a>関連項目

[#import 属性](../preprocessor/hash-import-attributes-cpp.md)\
[#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)
