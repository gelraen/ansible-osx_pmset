osx_pmset
=========

Calls `pmset` to change power management configurtion on Mac OS X.

Provided module, called `osx_pmset`, accepts two parameters: `on_battery` and
`on_charger`. Each of them is a dict with key-value pairs as provided by
`pmset -g custom`.

Example Playbook
----------------

1. Install this role via Ansible Galaxy:

    ```
    ansible-galaxy install gelraen.osx_pmset
    ```

2. Add it as a dependency for your own role in `meta/main.yml`:

	```
	dependencies:
	- gelraen.osx_pmset
	```

3. Use `osx_pmset` module as usual in your tasks:

	```
	- name: "Increase standby delays on low/high battery charge to 24h/48h respectively"
      osx_pmset:
        on_battery:
          standbydelayhigh: "{{ 48*3600 }}"
          standbydelaylow: "{{ 24*3600 }}"
	```


License
-------

MIT
