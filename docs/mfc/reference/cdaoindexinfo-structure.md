---
description: '詳細については、次を参照してください: CDaoIndexInfo 構造体'
title: CDaoIndexInfo 構造体
ms.date: 06/25/2018
f1_keywords:
- CDaoIndexInfo
helpviewer_keywords:
- DAO (Data Access Objects), Indexes collection
- CDaoIndexInfo structure [MFC]
ms.assetid: 251d8285-78ce-4716-a0b3-ccc3395fc437
ms.openlocfilehash: 2e09846789dc91e4d0df67665f3e975b557c07c8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97250765"
---
# <a name="cdaoindexinfo-structure"></a>CDaoIndexInfo 構造体

構造体には、 `CDaoIndexInfo` データアクセスオブジェクト (DAO) 用に定義されたインデックスオブジェクトに関する情報が含まれています。

## <a name="syntax"></a>構文

```cpp
struct CDaoIndexInfo {
    CDaoIndexInfo();                    // Constructor
    CString m_strName;                  // Primary
    CDaoIndexFieldInfo* m_pFieldInfos;  // Primary
    short m_nFields;                    // Primary
    BOOL m_bPrimary;                    // Secondary
    BOOL m_bUnique;                     // Secondary
    BOOL m_bClustered;                  // Secondary
    BOOL m_bIgnoreNulls;                // Secondary
    BOOL m_bRequired;                   // Secondary
    BOOL m_bForeign;                    // Secondary
    long m_lDistinctCount;              // All

    // Below the // Implementation comment:
    // Destructor, not otherwise documented
};
```

### <a name="parameters"></a>パラメーター

*m_strName*<br/>
Field オブジェクトに一意の名前を入力します。 詳細については、DAO ヘルプの「Name プロパティ」を参照してください。

*m_pFieldInfos*<br/>
インデックス内のキーフィールドがどのテーブルテーブルまたはレコードセットフィールドであるかを示す [CDaoIndexFieldInfo](../../mfc/reference/cdaoindexfieldinfo-structure.md) オブジェクトの配列へのポインター。 各オブジェクトは、インデックス内の1つのフィールドを識別します。 既定のインデックスの順序は昇順です。 インデックスオブジェクトには、各レコードのインデックスキーを表す1つ以上のフィールドを含めることができます。 昇順、降順、または組み合わせを指定できます。

*m_nFields*<br/>
に格納されているフィールドの数 `m_pFieldInfos` 。

*m_bPrimary*<br/>
プライマリプロパティが TRUE の場合、インデックスオブジェクトはプライマリインデックスを表します。 プライマリインデックスは、テーブル内のすべてのレコードを定義済みの順序で一意に識別する1つ以上のフィールドで構成されます。 インデックスフィールドは一意である必要があるため、DAO ではインデックスオブジェクトの Unique プロパティも TRUE に設定されています。 プライマリインデックスが複数のフィールドで構成されている場合、各フィールドに重複する値を含めることができますが、すべてのインデックス付きフィールドの値の組み合わせは一意である必要があります。 プライマリインデックスは、テーブルのキーで構成され、通常は主キーと同じフィールドを含んでいます。

テーブルの主キーを設定すると、主キーがテーブルのプライマリインデックスとして自動的に定義されます。 詳細については、DAO ヘルプの「プライマリプロパティ」と「一意のプロパティ」を参照してください。

> [!NOTE]
> テーブルには、最大で1つのプライマリインデックスを作成できます。

*m_bUnique*<br/>
インデックスオブジェクトがテーブルの一意のインデックスを表すかどうかを示します。 このプロパティが TRUE の場合、インデックスオブジェクトは一意のインデックスを表します。 一意インデックスは、定義済みの一意の順序でテーブル内のすべてのレコードを論理的に配置する1つ以上のフィールドで構成されます。 インデックスが1つのフィールドで構成されている場合、そのフィールドの値はテーブル全体で一意である必要があります。 インデックスが複数のフィールドで構成されている場合は、各フィールドに重複する値を含めることができますが、すべてのインデックス付きフィールドの値の組み合わせは一意である必要があります。

インデックスオブジェクトの Unique プロパティと Primary プロパティの両方が TRUE に設定されている場合、インデックスは一意であり、プライマリになります。これにより、テーブル内のすべてのレコードが定義済みの論理的な順序で一意に識別されます。 プライマリプロパティが FALSE に設定されている場合、インデックスはセカンダリインデックスになります。 セカンダリインデックス (キーと非キー) は、テーブル内のレコードの識別子としてではなく、定義済みの順序でレコードを論理的に配置します。

詳細については、DAO ヘルプの「プライマリプロパティ」と「一意のプロパティ」を参照してください。

*m_bClustered*<br/>
インデックスオブジェクトがテーブルのクラスター化インデックスを表すかどうかを示します。 このプロパティが TRUE の場合、インデックスオブジェクトはクラスター化インデックスを表します。それ以外の場合は、そうではありません。 クラスター化インデックスは、1つまたは複数の非キーフィールドで構成され、テーブル内のすべてのレコードを事前に定義された順序で配置します。 クラスター化インデックスを使用すると、テーブル内のデータは、そのクラスター化インデックスによって指定された順序で文字どおり格納されます。 クラスター化インデックスを使用すると、テーブル内のレコードに効率的にアクセスできます。 詳細については、DAO ヘルプの「Clustered Property」を参照してください。

> [!NOTE]
> Jet データベースエンジンではクラスター化インデックスがサポートされていないため、Microsoft Jet データベースエンジンを使用するデータベースでは、Clustered プロパティは無視されます。

*m_bIgnoreNulls*<br/>
インデックスフィールドに Null 値を持つレコードのインデックスエントリがあるかどうかを示します。 このプロパティが TRUE の場合、Null 値を持つフィールドにはインデックスエントリがありません。 フィールドを使用してレコードをすばやく検索するには、フィールドのインデックスを定義します。 インデックス付きフィールドで Null エントリを許可し、エントリの多くを Null にする場合は、インデックスオブジェクトの IgnoreNulls プロパティを TRUE に設定して、インデックスが使用するストレージ領域の量を減らすことができます。 次の表に示すように、IgnoreNulls プロパティの設定と必要なプロパティの設定を一緒に使用すると、インデックス値が Null のレコードにインデックスエントリがあるかどうかが決まります。

|IgnoreNulls|必須|インデックスフィールドに Null があります|
|-----------------|--------------|-------------------------|
|正しい|誤り|Null 値は許容されます。インデックスエントリが追加されていません。|
|False|False|Null 値は許容されます。インデックスエントリが追加されました。|
|True または False|はい|Null 値は使用できません。インデックスエントリが追加されていません。|

詳細については、DAO ヘルプの「IgnoreNulls プロパティ」を参照してください。

*m_bRequired*<br/>
DAO インデックスオブジェクトが Null 以外の値を必要とするかどうかを示します。 このプロパティが TRUE の場合、index オブジェクトでは Null 値が許可されません。 詳細については、DAO ヘルプの「必須プロパティ」を参照してください。

> [!TIP]
> このプロパティを、DAO インデックスオブジェクトまたは (テーブルテーブル、レコードセット、または querydef オブジェクトに含まれる) フィールドオブジェクトに対して設定できる場合は、フィールドオブジェクトに設定します。 Field オブジェクトのプロパティ設定の有効性は、インデックスオブジェクトの前にチェックされます。

*m_bForeign*<br/>
インデックスオブジェクトがテーブル内の外部キーを表すかどうかを示します。 このプロパティが TRUE の場合、インデックスはテーブル内の外部キーを表します。 外部キーは、主テーブル内の行を一意に識別する外部テーブル内の1つ以上のフィールドで構成されます。 Microsoft Jet データベースエンジンは、外部テーブルのインデックスオブジェクトを作成し、参照整合性を適用するリレーションシップを作成するときに、外部プロパティを設定します。 詳細については、DAO ヘルプの「外部プロパティ」を参照してください。

*m_lDistinctCount*<br/>
関連付けられたテーブルに含まれるインデックスオブジェクトの一意な値の数を示します。 DistinctCount プロパティを調べて、インデックス内の一意の値 (キー) の数を確認します。 インデックスで重複する値が許可されている場合、その値が複数回出現する可能性がある場合でも、キーは1回だけカウントされます。 この情報は、インデックス情報を評価することによってデータアクセスの最適化を試みるアプリケーションで役立ちます。 一意の値の数は、インデックスオブジェクトのカーディナリティとも呼ばれます。 DistinctCount プロパティには、特定の時間における実際のキー数が常に反映されるとは限りません。 たとえば、トランザクションのロールバックによって発生する変更は、DistinctCount プロパティにすぐには反映されません。 詳細については、DAO ヘルプの「DistinctCount プロパティ」を参照してください。

## <a name="remarks"></a>解説

上記の Primary、Secondary、および All への参照は、 `GetIndexInfo` [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getindexinfo) および [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getindexinfo)クラスのメンバー関数によって情報がどのように返されるかを示しています。

MFC クラスでは、インデックスオブジェクトは表されません。 代わりに、 [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) クラスまたは [CDAORECORDSET](../../mfc/reference/cdaorecordset-class.md) クラスの MFC オブジェクトの基になる DAO オブジェクトには、Indexes コレクションと呼ばれるインデックスオブジェクトのコレクションが含まれています。 これらのクラスは、インデックス情報の個々の項目にアクセスするためのメンバー関数を提供し `CDaoIndexInfo` `GetIndexInfo` ます。また、親オブジェクトのメンバー関数を呼び出すことによって、オブジェクトを使用して一度にすべてのオブジェクトにアクセスすることもできます。

`CDaoIndexInfo` には、のインデックスフィールド情報を適切に割り当ておよび割り当て解除するためのコンストラクターとデストラクターがあり `m_pFieldInfos` ます。

Tabledef オブジェクトのメンバー関数によって取得された情報 `GetIndexInfo` は、構造体に格納され `CDaoIndexInfo` ます。 `GetIndexInfo`インデックスオブジェクトが格納されているインデックスのコレクションを持つ、を含んでいる tabledef オブジェクトのメンバー関数を呼び出します。 `CDaoIndexInfo` は、 `Dump` デバッグビルドでメンバー関数も定義します。 を使用すると、 `Dump` オブジェクトの内容をダンプでき `CDaoIndexInfo` ます。

## <a name="requirements"></a>要件

**ヘッダー:** afxdao

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック、およびメッセージマップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoTableDef:: GetIndexInfo](../../mfc/reference/cdaotabledef-class.md#getindexinfo)
