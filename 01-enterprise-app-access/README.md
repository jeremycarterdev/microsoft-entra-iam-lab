# Enterprise Application Access Management

## Scenario

A Finance employee, Sarah Miller, requires access to an internal Finance application.

The goal of this lab was to configure application access in Microsoft Entra ID while following least-privilege principles and documenting how access could be managed throughout the user's identity lifecycle.

## Environment

- Microsoft Entra ID
- Microsoft Entra Admin Center
- Cloud-only identities
- Security groups
- Enterprise applications

## Existing Identity Configuration

Sarah Miller was configured as a standard member account within the Microsoft Entra tenant.

She was added to the following security group:

`SG-Finance-App-Users`

The security group was created to represent authorized Finance users who require access to Finance resources.

Sarah was not assigned any administrative roles because her job responsibilities did not require administrative privileges.

## Enterprise Application

I created a non-gallery enterprise application named:

`Black Tide Finance Portal`

This application represents an internal Finance application that should only be accessible to authorized users.

## Application Access

The preferred design was to assign the `SG-Finance-App-Users` security group to the enterprise application.

This would allow application access to be controlled through group membership rather than individual user assignments.

However, my current Microsoft Entra licensing level does not support group-based assignment to enterprise applications.

Because of this licensing limitation, Sarah Miller was assigned directly to the Black Tide Finance Portal.

## Preferred Access Model

The preferred configuration would be:

Sarah Miller  
↓  
SG-Finance-App-Users  
↓  
Black Tide Finance Portal

This design would simplify access management because adding or removing a user from the Finance security group would automatically control their application access.

## Identity Lifecycle Considerations

If Sarah transferred from Finance to another department, I would:

1. Remove her direct access to the Finance application.
2. Remove her from the Finance security group.
3. Add her to the appropriate security group for her new department.
4. Update relevant identity attributes if required.
5. Verify that Finance access was removed.
6. Verify that her new group memberships and access were correct.
7. Document the changes before closing the request.

This follows least-privilege principles by ensuring users retain only the access required for their current job responsibilities.

## Key Takeaways

This lab provided hands-on experience with:

- Microsoft Entra user administration
- Security group membership
- Enterprise applications
- Application assignments
- Direct vs. group-based access
- Least privilege
- Joiner-Mover-Leaver (JML) lifecycle concepts
- Identifying and adapting to licensing limitations
- Access verification
