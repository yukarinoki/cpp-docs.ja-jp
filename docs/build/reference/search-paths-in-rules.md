---
description: 詳細については、「ルール内の検索パス」を参照してください。
title: 規則の検索パス
ms.date: 11/04/2016
helpviewer_keywords:
- search paths in NMAKE inference rules
- inference rules in NMAKE
- rules, inference
ms.assetid: 38feded6-536d-425d-bf40-fff3173a5506
ms.openlocfilehash: bf070fc57907b68eb458b8a5276698282ef30f9d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224882"
---
# <a name="search-paths-in-rules"></a>規則の検索パス

```
{frompath}.fromext{topath}.toext:
   commands
```

## <a name="remarks"></a>解説

推論規則は、依存関係に指定されたパスが推論規則のパスと完全に一致する場合にのみ、依存関係に適用されます。 *Frompath* に依存するディレクトリを指定し、 *topath*; でターゲットのディレクトリを指定します。スペースは使用できません。 各拡張機能に指定できるパスは1つだけです。 1つの拡張機能のパスには、他方のパスが必要です。 現在のディレクトリを指定するには、ピリオド (.) または空の中かっこ ({}) のいずれかを使用します。 マクロは、 *frompath* および *topath* を表すことができます。これらは、プリプロセス中に呼び出されます。

## <a name="example"></a>例

### <a name="code"></a>コード

```
{dbi\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $(YUDBI) $<

{ilstore\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $<

{misc\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $(YUPDB) $<

{misc\}.c{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $<

{msf\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $<

{bsc\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $(YUPDB) $<

{mre\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $(YUPDB) $<

{namesrvr\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $(YUPDB) $<

{src\cvr\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $<
```

## <a name="see-also"></a>関連項目

[ルールの定義](defining-a-rule.md)
