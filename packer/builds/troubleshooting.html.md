---
title: "Troubleshooting Failing Builds"
---

## Troubleshooting Failing Builds

Packer builds can fail in Atlas for a number of reasons – improper
configuration, transient networking errors, and hardware constraints
are all possible. Below is a list of debugging options you can use.

### Verbose Packer Logging

You can [set a variable](/help/packer/builds/build-environment#environment-variables) in the UI that increases the logging verbosity
in Packer. Set the `PACKER_LOG` key to a value of `1` to accomplish this.

After setting the variable, you'll need to [rebuild](/help/packer/builds/rebuilding).

Verbose logging will be much louder than normal Packer logs and isn't
recommended for day-to-day operations. Once enabled, you'll be able to
see in futher detail why things failed or what operations Packer was performing.

This can also be used locally:

    PACKER_LOG=1 packer build ...


### Hardware Limitations

Your build may be failing by requesting larger memory or
disk usage then is available. Read more about the [build environment](/help/packer/builds/build-environment#hardware-limitations).

### Local Debugging

Sometimes it's faster to debug failing builds locally. In this case,
you'll want to [install Packer](/help/intro/updating-tools) and any providers (like Virtualbox) necessary.

Because Atlas runs the open source version of Packer, there should be
no difference in execution between the two, other than the environment that
Packer is running in. For more on hardware constraints in the Atlas environment
read below.

Once your builds are running smoothly locally you can push it up to Atlas
for versioning and automated builds.

### Community Resources

Packer is an open source project with an active community. If you're
having an issue specific to Packer, the best avenue for support is
the mailing list or IRC. All bug reports should go to GitHub.

- Website: [packer.io](https://packer.io)
- GitHub: [github.com/mitchellh/packer](https://github.com/mitchellh/packer)
- IRC: `#packer-tool` on Freenode
- Mailing list: [Google Groups](http://groups.google.com/group/packer-tool)

### Getting Support

If you believe your build is failing as a result of a bug in Atlas,
or would like other support, please [email us](mailto:support@hashicorp.com).
