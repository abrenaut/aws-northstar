### Examples

```jsx
import Table from 'aws-northstar/components/Table';
import StatusIndicator from 'aws-northstar/components/StatusIndicator';

const columnDefinitions = [
    {
        id: 'id',
        width: 200,
        Header: 'Id',
        accessor: 'id'
    },
    {
        id: 'name',
        width: 200,
        Header: 'Name',
        accessor: 'name'
    },
    {
        id: 'accounts',
        width: 200,
        Header: '# Accounts',
        accessor: 'accounts.length'
    },
    {
        id: 'status',
        width: 200,
        Header: 'Status',
        accessor: 'status',
        Cell: ({ row  }) => {
            if (row && row.original) {
                const status = row.original.status;
                switch(status) {
                    case 'active':
                        return <StatusIndicator  statusType='positive'>Active</StatusIndicator>;
                    case 'inactive':
                        return <StatusIndicator  statusType='negative'>Inactive</StatusIndicator>;
                    default:
                        return null;
                }
            }
            return row.id;
        }
    }
];

const data = [
    {
        id: 'id0000001',
        name: 'Engagement one',
        accounts: [],
        status: 'active'
    },
    {
        id: 'id0000002',
        name: 'Engagement two',
        accounts: ['acc1', 'acc2'],
        status: 'active'
    },
    {
        id: 'id0000003',
        name: 'Engagement three',
        accounts: ['acc1', 'acc2'],
        status: 'inactive'
    },
    {
        id: 'id0000004',
        name: 'Engagement four',
        accounts: ['acc1', 'acc2', 'acc3'],
        status: 'inactive'
    },
    {
        id: 'id0000005',
        name: 'Engagement five',
        accounts: [],
        status: 'inactive'
    },
    {
        id: 'id0000006',
        name: 'Engagement six',
        accounts: [],
        status: 'active'
    },
    {
        id: 'id0000007',
        name: 'Engagement seven',
        accounts: [],
        status: 'active'
    },
    {
        id: 'id0000008',
        name: 'Engagement eight',
        accounts: [],
        status: 'active'
    },
    {
        id: 'id0000009',
        name: 'Engagement nine',
        accounts: [],
        status: 'active'
    },
    {
        id: 'id0000010',
        name: 'Engagement ten',
        accounts: [],
        status: 'active'
    },
    {
        id: 'id0000011',
        name: 'Engagement eleven',
        accounts: ['acc1', 'acc4', 'acc5', 'acc7'],
        status: 'active'
    }
];

<Table
    onSelectionChange={()=> {}}
    tableTitle='Basic Table'
    columnDefinitions={columnDefinitions}
    items={data}
    disableGroupBy={true}
    disableSettings={true}
    disablePagination={true}
    disableFilters={true}
    disableRowSelect={true}
    disableSortBy={true}
/>

```

```jsx
import Table from 'aws-northstar/components/Table';

const columnDefinitions = [
    {
        id: 'id',
        width: 200,
        Header: 'Id',
        accessor: 'id'
    },
    {
        id: 'name',
        width: 200,
        Header: 'Name',
        accessor: 'name'
    },
    {
        id: 'accounts',
        width: 200,
        Header: '# Accounts',
        accessor: 'accounts.length'
    }
];

<Table
    tableTitle='Loading'
    loading={true}
    columnDefinitions={columnDefinitions}
    disableGroupBy={true}
    disableSettings={true}
    disablePagination={true}
    disableFilters={true}
    disableRowSelect={true}
    disableSortBy={true}
    />
```

```jsx
import Table from 'aws-northstar/components/Table';
import StatusIndicator from 'aws-northstar/components/StatusIndicator';
import Button from 'aws-northstar/components/Button';
import Inline from 'aws-northstar/layouts/Inline';

const columnDefinitions = [
    {
        id: 'id',
        width: 200,
        Header: 'Id',
        accessor: 'id'
    },
    {
        id: 'name',
        width: 200,
        Header: 'Name',
        accessor: 'name'
    },
    {
        id: 'accounts',
        width: 200,
        Header: '# Accounts',
        accessor: 'accounts.length'
    },
    {
        id: 'status',
        width: 200,
        Header: 'Status',
        accessor: 'status',
        Cell: ({ row  }) => {
            if (row && row.original) {
                const status = row.original.status;
                switch(status) {
                    case 'active':
                        return <StatusIndicator  statusType='positive'>Active</StatusIndicator>;
                    case 'inactive':
                        return <StatusIndicator  statusType='negative'>Inactive</StatusIndicator>;
                    default:
                        return null;
                }
            }
            return null;
        }
    }
];

const data = [
    {
        id: 'id0000001',
        name: 'Engagement one',
        accounts: [],
        status: 'active'
    },
    {
        id: 'id0000002',
        name: 'Engagement two',
        accounts: ['acc1', 'acc2'],
        status: 'active'
    },
    {
        id: 'id0000003',
        name: 'Engagement three',
        accounts: ['acc1', 'acc2'],
        status: 'inactive'
    },
    {
        id: 'id0000004',
        name: 'Engagement four',
        accounts: ['acc1', 'acc2', 'acc3'],
        status: 'inactive'
    },
    {
        id: 'id0000005',
        name: 'Engagement five',
        accounts: [],
        status: 'inactive'
    },
    {
        id: 'id0000006',
        name: 'Engagement six',
        accounts: [],
        status: 'active'
    },
    {
        id: 'id0000007',
        name: 'Engagement seven',
        accounts: [],
        status: 'active'
    },
    {
        id: 'id0000008',
        name: 'Engagement eight',
        accounts: [],
        status: 'active'
    },
    {
        id: 'id0000009',
        name: 'Engagement nine',
        accounts: [],
        status: 'active'
    },
    {
        id: 'id0000010',
        name: 'Engagement ten',
        accounts: [],
        status: 'active'
    },
    {
        id: 'id0000011',
        name: 'Engagement eleven',
        accounts: ['acc1', 'acc4', 'acc5', 'acc7'],
        status: 'active'
    }
];

const tableActions = (
    <Inline>
        <Button onClick={() => alert('Delete button clicked')}>
            Delete
        </Button>
        <Button variant='primary' onClick={() => alert('Add button clicked')}>
            Add
        </Button>
    </Inline>
);

<Table
    actionGroup={tableActions}
    tableTitle='Multi Select Table'
    columnDefinitions={columnDefinitions}
    items={data}
    onSelectionChange={console.log}
    getRowId={React.useCallback(data => data.id, [])}
    sortBy={[{
        id: 'name',
        desc: true
    }]}
/>
```

```jsx
import Table from 'aws-northstar/components/Table';
import StatusIndicator from 'aws-northstar/components/StatusIndicator';
import Button from 'aws-northstar/components/Button';
import Inline from 'aws-northstar/layouts/Inline';

const columnDefinitions = [
    {
        id: 'id',
        width: 200,
        Header: 'Id',
        accessor: 'id'
    },
    {
        id: 'name',
        width: 200,
        Header: 'Name',
        accessor: 'name'
    },
    {
        id: 'accounts',
        width: 200,
        Header: '# Accounts',
        accessor: 'accounts.length'
    },
    {
        id: 'status',
        width: 200,
        Header: 'Status',
        accessor: 'status',
        Cell: ({ row  }) => {
            if (row && row.original) {
                const status = row.original.status;
                switch(status) {
                    case 'active':
                        return <StatusIndicator  statusType='positive'>Active</StatusIndicator>;
                    case 'inactive':
                        return <StatusIndicator  statusType='negative'>Inactive</StatusIndicator>;
                    default:
                        return null;
                }
            }
            return null;
        }
    }
];

const data = [
    {
        id: 'id0000001',
        name: 'Engagement one',
        accounts: [],
        status: 'active'
    },
    {
        id: 'id0000002',
        name: 'Engagement two',
        accounts: ['acc1', 'acc2'],
        status: 'active'
    },
    {
        id: 'id0000003',
        name: 'Engagement three',
        accounts: ['acc1', 'acc2'],
        status: 'inactive'
    },
    {
        id: 'id0000004',
        name: 'Engagement four',
        accounts: ['acc1', 'acc2', 'acc3'],
        status: 'inactive'
    },
    {
        id: 'id0000005',
        name: 'Engagement five',
        accounts: [],
        status: 'inactive'
    },
    {
        id: 'id0000006',
        name: 'Engagement six',
        accounts: [],
        status: 'active'
    },
    {
        id: 'id0000007',
        name: 'Engagement seven',
        accounts: [],
        status: 'active'
    },
    {
        id: 'id0000008',
        name: 'Engagement eight',
        accounts: [],
        status: 'active'
    },
    {
        id: 'id0000009',
        name: 'Engagement nine',
        accounts: [],
        status: 'active'
    },
    {
        id: 'id0000010',
        name: 'Engagement ten',
        accounts: [],
        status: 'active'
    },
    {
        id: 'id0000011',
        name: 'Engagement eleven',
        accounts: ['acc1', 'acc4', 'acc5', 'acc7'],
        status: 'active'
    }
];

const tableActions = (
    <Inline>
        <Button onClick={() => alert('Delete button clicked')}>
            Delete
        </Button>
        <Button variant='primary' onClick={() => alert('Add button clicked')}>
            Add
        </Button>
    </Inline>
);

 <Table
    actionGroup={tableActions}
    tableTitle='Single Select Table'
    multiSelect={false}
    columnDefinitions={columnDefinitions}
    items={data}
    onSelectionChange={console.log}
    getRowId={React.useCallback(data => data.id, [])}
/>
```

```jsx
import Table from 'aws-northstar/components/Table';
import { useMemo, useState, useCallback } from 'react';
import orderBy from 'lodash.orderby';

const columnDefinitions = [
    {
        id: 'id',
        width: 200,
        Header: 'Id',
        accessor: 'id'
    },
    {
        id: 'name',
        width: 200,
        Header: 'Name',
        accessor: 'name'
    },
];

const [items, setItems] = useState([]);
const [rowCount, setRowCount] = useState(0);
const [loading, setLoading] = useState(false);
const fetchIdRef = React.useRef(0);
const data = useMemo(() => {
    const data = [];
    for (let i = 0; i < 1000; i++) {
        data.push({
            id: i,
            name: `Name ${i}`,
        });
    }

    return data;
}, []);
const handleFetchData = useCallback(options => {
    setLoading(true);
    const fetchId = ++fetchIdRef.current;
    setTimeout(() => {
        if (fetchId === fetchIdRef.current) {
            // You could fetch your data from server.
            const filterData = data.filter(d => {
                if (options.filterText) {
                    return d.name.indexOf(options.filterText) > 0;
                }

                return true;
            });
            let tempData = filterData.slice(
                options.pageIndex * options.pageSize,
                (options.pageIndex + 1) * options.pageSize
            );
            if(options.sortBy && options.sortBy.length > 0) {
                tempData = orderBy(tempData, options.sortBy[0].id, options.sortBy[0].desc ? 'desc': 'asc');
            }
            setItems(tempData);
            setRowCount(filterData.length);
            setLoading(false);
        }
    }, 1000);
}, []);

<Table
    tableTitle='Remote Update Table'
    columnDefinitions={columnDefinitions}
    onFetchData={handleFetchData}
    rowCount={rowCount}
    items={items}
    loading={loading}
/>
```

```jsx
import Table from 'aws-northstar/components/Table';

const columnDefinitions = [
    {
        id: 'id',
        width: 200,
        Header: 'Id',
        accessor: 'id'
    },
    {
        id: 'name',
        width: 200,
        Header: 'Name',
        accessor: 'name'
    },
    {
        id: 'accounts',
        width: 200,
        Header: '# Accounts',
        accessor: 'accounts.length'
    }
];

<Table
    tableTitle='Error'
    errorText='Something went wrong. Please try again later.'
    columnDefinitions={columnDefinitions}
    disableGroupBy={true}
    disableSettings={true}
    disablePagination={true}
    disableFilters={true}
    disableRowSelect={true}
    disableSortBy={true}
    />
```
