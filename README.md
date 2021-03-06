Role Name
=========

Ansible role to install the JumpCloud Agent. This role was inspired by modcloth's SumoCollector role and the RO NewRelic Role.

To install the role as part of an AMI build:

```ansible
- role: reactiveops.jcagent
  jumpcloud_image_build: true
  jumpcloud_tag: false
  become: true
```

To skip the install and only tag:
```ansible
- role: reactiveops.jcagent
  jumpcloud_image_build: false
  jumpcloud_install: false
  jumpcloud_tag: true
  jumpcloud_tag_name: 'pretzels'
  become: true
```

## Variables

- `jumpcloud_connect_key` provides the X-Connect-Key that JumpCloud expects for authorization. default: `''`
- `jumpcloud_image_build` if `true` will clean up registration information as part of an image build. default: `false`
- `jumpcloud_install` determines if jumpcloud install should be run. default: `true`
- `jumpcloud_tag` will tag the system if set to `true`. default: `false`
- `jumpcloud_tag_name` is the tag to apply. default: `jumpcloud`
- `jumpcloud_bundle_command` allows overriding the bundle command, which can include the path. default: `bundle`
- `jumpcloud_bundler_command` allows overriding the bundler command, which can include the path. default: `bundler`
- `jumpcloud_shutdown_cleanup` determines if an init script that de-registers the system on shutdown is installed. default: `false`
- `jumpcloud_shutdown_cleanup_delete` whether to delete the instance from jumpcloud. default: `false`. this will only happen if `jumpcloud_shutdown_cleanup` is set to `true`.


License
-------

MIT
